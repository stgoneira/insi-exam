# Examen INSI

A todos los recursos ejecutables se les puede cambiar el puerto de ejecución pasando un argumento a la ejecución, por ejemplo:

```
SistemaX.exe <puerto>
```

## XML Pagos

Se entregan 3 archivos XML para poder utilizar en el desarrollo de la solución.


## Web Pagos

Puerto por defecto 5000. Cuenta con la siguiente API Rest:

* GET /api/payments
* GET /api/payments/today


## Sistema Contable (SOAP)

WSDL: http://localhost:5001/?wsdl

Puerto por defecto 5001. Sistema solo para Windows. Para ejecutar debe:

```
.\SistemaContable.exe <puerto>
```

Cuenta con un método:

* RegistrarPago(clienteId, monto)

El cual devuelve el estado de cuenta: clienteId y el saldo.

Donde un saldo mayor que cero quiere decir que el cliente aún tiene deuda, por el contrario, si el saldo es cero o menor, quiere decir que el cliente está al día o ha pagado por adelantado.



## Sistema Agendamiento (SOAP)

WSDL en: http://localhost:5002/AgendaService?wsdl

Sistema SOAP para agendar clases en el gimnasio. Por defecto, ejecuta en el puerto 5002. Debe tener instalado dotNET 8 para su ejecución, idealmente correrlo en Linux usando el siguiente comando:

```
dotnet SistemaAgendamientoClases.dll <puerto>
```

Tiene disponible 2 métodos:

* HabilitarUsuario(clienteId)
* DeshabilitarUsuario(clienteId)



## Sistema Control de Acceso

Puede ejecutarse en Linux usando:

```
dotnet SistemaControlAcceso.dll
```

El Sistema de Control de Accesos tiene una API REST:

* GET /api/users - recuperar usuarios
* POST /api/users - crear un usuario nuevo
* GET /api/users/{rut} - recuperar un usuario en particular
* PATCH /api/users/{rut} - actualizar información de un usuario
* DELETE /api/users/{rut} - eliminar un usuario

Espera JSON con la siguiente estructura:

```
{
  "rut": "string",
  "nombre": "string",
  "email": "string",
  "telefono": "string",
  "habilitado": boolean
}
```
