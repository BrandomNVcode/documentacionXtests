# Descripción

Te genera una cotización en base a una lista de codigo de productos con su cantidad que el usuario quiere comprar.
Busca en la tabla PRODUCTO de la base de datos por el codigo de producto para extraer el campo 'precio'.
Una vez obtenidos los precios de la lista de producto calcula el costo total que vendria a ser la suma de todos los productos
por la cantidad que el usuario quiere comprar.
Como respuesta correcta te da un status 200 y te genera un codigo de pago llamado 'codigoPago' y el total a pagar llamado 'precioTotal'. Estos valores
se almacenan en la tabla COTIZACION de la base de datos en los campos 'codigoPago' y 'precioTotal'.


#### Curl:

```bash
curl -X 'POST' \
  'https://ms-ne-pagos/v1/cotizacion' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "producto": [
    {"codigo": "123", "cantidad": 2}
  ],
  "descuento": true
}'
```

### Response:
```json
{
    "codigoPago": "ee11a56e-3e15-4627-b465-30b245bc1c22",
    "precioTotal": 30.25
}
```


#### Reglas:

* producto: 
    - Este campo es un array y no puede estar vacio, sino devuelve un status 400.
* codigo:
    - El codigo de producto es un string.
    - solo alfanumerico de 10 caracteres.
* cantidad:
    - Representa la cantidad a comprar.
    - Es un valor numerico entero.
    - No puede ser negativo ni cero sino devuelve status 400.
* codigoPago:
    - Es un valor uuid.
* precioTotal:
    - Es un valor numerico de hasta 2 decimales.
* descuento:
    - Es un valor booleano


