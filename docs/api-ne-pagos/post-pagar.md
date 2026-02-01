# Descripción

Registra un pago en la base de datos en la tabla PAGO, donde almacena el codigo de la cotizacion y la cantidad a pagar.
Da como respuesta correcta un status 200 y el codigo de compra.


#### Curl:

```bash
curl -X 'POST' \
  'https://ms-ne-pagos/v1/pagar' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "codigoPago": "ee11a56a-3e15-4627-b465-30b245bc1c22",
  "precioTotal" 458.54
}'
```

### Response:
```json
{
    "codigoCompra": "ee11a56e-3e15-4620-b465-30b245bc1c22"
}
```

#### Reglas:

* codigoPago:
    - Es un valor uuid proveniente del endpoint POST /cotizacion
* precioTotal:
    - Es un valor numerico de hasta 2 decimales proveniente del endpoint POST /cotizacion.
* codigoCompra:
    - Es un valor uuid.

