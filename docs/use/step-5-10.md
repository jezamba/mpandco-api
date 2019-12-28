[<- Regresar a la documentación]({{site.baseurl}}/)

<div id="step510"></div>
## 6.10. Agregar Registro de Multipagos.

Este metodo permite crear elementos(items) de un lote que esté **pendiente por cargar**

**Importante**: Si el usuario no tiene un lote creado, el metodo automaticamente crea un lote de tipo dispersión en estado **pendiente por cargar**, y a dicho lote le agrega el elemento(item) cargado.

URL: `api/multipayment/register-item.json`

Método HTTP: `POST`

Parametros: `type` = `DISPERSION` 

### Datos minimos a enviar

  {
      "multi_payment_item": {
          "reference": "0001",
          "nameAccount": "Witty Growth",
          "identificationNumber": "j54637469",
          "bankAccount": "01340000000000000000",
          "amount": "20",
          "phone": "4244569686",
          "email": "developer@mpandco.com"
      }
  }

### Ejemplo de Petición

  curl -X GET \
    'https://test.mpandco.com/api/multipayment/register-item.json?type=DISPERSION' \
    -H 'cache-control: no-cache' \
    -d '{
        "multi_payment_item": {
            "reference": "0001",
            "nameAccount": "Witty Growth",
            "identificationNumber": "j54637469",
            "bankAccount": "01340000000000000000",
            "amount": "20",
            "phone": "4244569686",
            "email": "developer@mpandco.com"
        }
    }'

### Respuesta
  
  {
    "ref":"MP19122800001",
    "identification_number":"j54637469",
    "status":"APPROVED"
  }

**Importante**: Debe verificar el estado de la respuesta sea **"APPROVED"**