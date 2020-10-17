## FlexBox 


 - Veremos las diferentes propiedades que nos ayudaran a entender mejor FlexBox


##  Dirección de los ejes 

 1. flex-direction	row | row-reverse | column | column-reverse	Cambia la orientación del eje principal.

  Valor	                          Descripción

- row	            Establece la dirección del eje principal en horizontal.

- row-reverse	    Establece la dirección del eje principal en horizontal (invertido).

- column	        Establece la dirección del eje principal en vertical.

- column-reverse	Establece la dirección del eje principal en vertical (invertido).



 2. flex-wrap	nowrap | wrap | wrap-reverse	Evita o permite el desbordamiento (multilinea).

   Valor	                           Descripción

-  nowrap	           Establece los ítems en una sola línea (no permite que se desborde el contenedor).

-  wrap	               Establece los ítems en modo multilínea (permite que se desborde el contenedor).

-  wrap-reverse	       Establece los ítems en modo multilínea, pero en dirección inversa.


Agamos un ejercicio con este codigo para ver las propiedades de flexbox 

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
  width: 400px;
  height: 400px;
  background: rgb(129, 178, 218);
    

}

.container > .item {

    background: #777;
    width: 50%;
    height: 50px;




}
```
















 



