## Propiedades de alineación Flexbox

1. justify-content: Se utiliza para alinear los ítems del eje principal (por defecto, el horizontal).
 
    Valor	                         Descripción

 - flex-start     	Agrupa los ítems al principio del eje principal.
 
 - flex-end	        Agrupa los ítems al final del eje principal.

 - center	        Agrupa los ítems al centro del eje principal.

 - space-between	Distribuye los ítems dejando el máximo espacio para separarlos.

 - space-around	    Distribuye los ítems dejando el mismo espacio alrededor de ellos (izq/dcha).

 - space-evenly	    Distribuye los ítems dejando el mismo espacio (solapado) a izquierda y derecha.




 2.  align-items Usada para alinear los ítems del eje secundario (por defecto, el vertical).




        Valor	      Descripción

 - flex-start	 Alinea los ítems al principio del eje secundario.

 - flex-end	     Alinea los ítems al final del eje secundario.

 - center    	 Alinea los ítems al centro del eje secundario.

 - stretch	     Alinea los ítems estirándolos de modo que cubran desde el inicio hasta el finqs del contenedor.

- baseline	     Alinea los ítems en el contenedor según la base del contenido de los ítems del contenedor.





3. align-content:  servirá para alinear cada una de las líneas del contenedor multilinea



    Valor	                      Descripción

- flex-start	         Agrupa los ítems al principio del eje principal.

- flex-end	             Agrupa los ítems al final del eje principal.

- center	             Agrupa los ítems al centro del eje principal.

- space-between	         Distribuye los ítems desde el inicio hasta el final.

- space-around	         Distribuye los ítems dejando el mismo espacio a los lados de cada uno.

- stretch	             Estira los ítems para ocupar de forma equitativa todo el espacio.



Veamos unos ejemplos de los valores de las propiedades de Flexbox con este codigo :

```html
<body>
  
   <div class="container">  
        <div class="item">1</div> 
        <div class="item">2</div>
        <div class="item">3</div>
        <div class="item">4</div> 
        <div class="item">5</div>
        <div class="item">6</div>
      </div>
  
</body>
```




```css

.container{ 
  display: flex;
  width: 100%;
  height: 200px;
  
  align-items: flex-end;
  
  background: rgb(129, 178, 218);
    

}

.container > .item {

    background: #777;
    width: 20%;
    height: 30px;
   

}






}
```

Veamos unos ejemplos de los valores de las propiedades de Flexbox con este codigo para cambiar la dimension de nuestros items  :


usaremos este codigo de html para el ejercicio de cada una de las propiedades;

 
```html
<body>

<div id="main" class="main">
   <div style="background-color:coral;"> 50px </div>
   <div style="background-color:lightblue;"> 100px</div>
   <div style="background-color:khaki;">50px</div>
   <div style="background-color:pink;"> 50px</div>
   <div style="background-color:rgb(218, 33, 64);"> 50px</div>
   <div style="background-color:lightgrey;">50px</div>
 </div>

  
   
  
</body>
```


## Propiedades para 



1. flex grow aumenta el tamaño de un item a su mismo tamaño las cantidad qu le indiquemos 


```css

   #main div:nth-of-type(1) {           
     
    flex-grow: 1;      
   
    }

   #main div:nth-of-type(2) {
    
    flex-grow: 3;
    
    }

   #main div:nth-of-type(3) {
    
    flex-grow: 1;

}

   #main div:nth-of-type(4) {
    
    flex-grow: 1;
}

 ```



2.  flex-shrink     Decremente su medida inicial el numero de veces que se le indique 

```css
#main div {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 100px;
}

#main div:nth-of-type(2) {
    flex-shrink: 3;
  }
 ```




3. flex-basis  Establezca la longitud inicial del item 

```css

#main div {
    flex-grow: 0;
    flex-shrink: 0;
    flex-basis: 50px;
  }

  
  #main div:nth-of-type(2) {
    flex-basis: 100px;
  }


```



