# Examen INSI

## XML Pagos

Se entregan 3 archivos XML para poder utilizar en el desarrollo de la solución.


## Web Pagos

Puerto por defecto 5000. Cuenta con la siguiente API Rest:

* GET /api/payments
* GET /api/payments/today

## Sistema Contable

Sistema solo para Windows. Debe ejecutar:

```
.\SistemaContable.exe <puerto>
```

RegistrarPago(clienteId, monto)

devuelve el estado de cuenta: clienteId y el saldo.

Donde un saldo mayor que cero quiere decir que el cliente aún tiene deuda, por el contrario, si el saldo es cero o menor, quiere decir que el cliente está al día o ha pagado por adelantado.

http://localhost:5001/?wsdl

## Sistema Agendamiento

Sistema SOAP para agendar clases en el gimnasio. Por defecto, ejecuta en el puerto 5002.

Archivo WSDL en: http://localhost:5002/AgendaService?wsdl

Tiene disponible 2 métodos:

* HabilitarUsuario(clienteId)
* DeshabilitarUsuario(clienteId)



## Sistema Control de Acceso

El Sistema de Control de Accesos tiene una API REST:

* GET /api/users
* POST /api/users
* GET /api/users/{rut}
* PATCH /api/users/{rut}
* DELETE /api/users/{rut}

Espera JSON con la siguiente estructura:

```
{
  "rut": "string",
  "nombre": "string",
  "email": "string",
  "telefono": "string",
  "habilitado": true
}
```
