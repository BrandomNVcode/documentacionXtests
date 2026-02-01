# API que ayuda a gestionar los pagos

## Esta api pose 2 endpoints principales


### 1. POST /cotizacion
Te genera una cotización en base a una lista de codigo de productos con su cantidad que el usuario quiere comprar.
Como respuesta de devuelve un codigo de pago y el precio total que son inputs para el metodo POST /pagar.

### 1. POST /pagar
Registra el pago de los productos. Recibe como request body el codigo de pago y precio total de la cotización.

