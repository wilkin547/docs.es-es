---
description: 'Más información acerca de: uso de JSONP'
title: Utilizar JSONP
ms.date: 03/30/2017
ms.assetid: f386718c-b4ba-4931-a610-40c27a46672a
ms.openlocfilehash: f4d21670cf468328b8579fa8a9cf2c2e06f09337
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632196"
---
# <a name="using-jsonp"></a>Utilizar JSONP

El relleno de JSON (JSONP) es un mecanismo que habilita el soporte de script entre sitios en exploradores web. JSONP está diseñado basándose en la capacidad de los exploradores web de cargar scripts desde un sitio diferente de aquel en el que se recuperó el documento cargado actualmente. El mecanismo funciona rellenando la carga útil de JSON con un nombre de la función de devolución de llamada definido por el usuario, como se muestra en el siguiente ejemplo.

```javascript
callback({"a" = \\"b\\"});
```

En el ejemplo anterior, la carga de JSON, `{"a" = \\"b\\"}`, se ajusta a una llamada de función, `callback`. La función de devolución de llamada ya debe estar definido en la página web actual. El tipo de contenido de una respuesta JSONP es `application/javascript` .

JSONP no está habilitado automáticamente. Para habilitarlo, establezca el atributo `javascriptCallbackEnabled` como `true` en uno de los puntos de conexión estándar HTTP (<xref:System.ServiceModel.Description.WebHttpEndpoint> o <xref:System.ServiceModel.Description.WebScriptEndpoint>), como se muestra en el siguiente ejemplo.

```xml
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint name="" javascriptCallbackEnabled="true"/>
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

El nombre de la función de devolución de llamada se puede especificar en una variable de consulta denominada devolución de llamada, tal y como se muestra en la siguiente dirección URL.

`http://baseaddress/Service/RestService?callback=functionName`

Cuando se invoca, el servicio envía una respuesta como la siguiente.

```javascript
functionName({"root":"Something"});
```  

También puede especificar el nombre de la función de devolución de llamada aplicando <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute> a la clase de servicio, como se muestra en el siguiente ejemplo.

```csharp
[ServiceContract]
[JavascriptCallbackBehavior(ParameterName = "$callback")]
public class Service1
{
    [OperationContract]
    [WebGet(ResponseFormat=WebMessageFormat.Json)]
    public string GetData()
    {
    }
}
```

En el servicio mostrado previamente, la solicitud tiene el aspecto siguiente.

`http://baseaddress/Service/RestService?$callback=anotherFunction`

Cuando se invoca, el servicio responde del modo siguiente.

```javascript
anotherFunction ({"root":"Something"});
```

## <a name="http-status-codes"></a>Códigos de estado HTTP

Las respuestas JSONP con códigos de estado HTTP distintos de 200 incluyen un segundo parámetro con la representación numérica del código de estado HTTP, como se muestra en el siguiente ejemplo.

```javascript
anotherFunction ({"root":"Something"}, 201);
```

## <a name="validations"></a>Validaciones

Se realizan las siguientes validaciones cuando JSONP está habilitado:

- La infraestructura de WCF produce una excepción si `javascriptCallback` está habilitado, existe un parámetro de cadena de consulta de devolución de llamada en la solicitud, y el formato de la respuesta está establecido en JSON.

- Si la solicitud contiene el parámetro de cadena de consulta de devolución de llamada, pero la operación no es un HTTP GET, se omite el parámetro de devolución de llamada.

- Si el nombre de devolución de llamada es `null` o una cadena vacía, la respuesta no obtiene el formato JSONP.

## <a name="see-also"></a>Vea también

- [Información general del modelo de programación web HTTP de WCF](wcf-web-http-programming-model-overview.md)
