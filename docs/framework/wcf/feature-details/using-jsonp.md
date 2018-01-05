---
title: Utilizar JSONP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f386718c-b4ba-4931-a610-40c27a46672a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3cd0d20f619444b2a00fccafdf63557b5e09e21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-jsonp"></a><span data-ttu-id="4a3b4-102">Utilizar JSONP</span><span class="sxs-lookup"><span data-stu-id="4a3b4-102">Using JSONP</span></span>

<span data-ttu-id="4a3b4-103">El relleno de JSON (JSONP) es un mecanismo que habilita el soporte de script entre sitios en exploradores web.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-103">JSON Padding (JSONP) is a mechanism that enables cross-site scripting support in Web browsers.</span></span> <span data-ttu-id="4a3b4-104">JSONP está diseñado basándose en la capacidad de los exploradores web de cargar scripts desde un sitio diferente de aquel en el que se recuperó el documento cargado actualmente.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-104">JSONP is designed around the ability of Web browsers to load scripts from a site different from the one the current loaded document was retrieved from.</span></span> <span data-ttu-id="4a3b4-105">El mecanismo funciona rellenando la carga útil de JSON con un nombre de la función de devolución de llamada definido por el usuario, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-105">The mechanism works by padding the JSON payload with a user-defined callback function name, as shown in the following example.</span></span>

```javascript
callback({"a" = \\"b\\"});
```

<span data-ttu-id="4a3b4-106">En el ejemplo anterior, la carga de JSON, `{"a" = \\"b\\"}`, se ajusta a una llamada de función, `callback`.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-106">In the preceding example the JSON payload, `{"a" = \\"b\\"}`, is wrapped in a function call, `callback`.</span></span> <span data-ttu-id="4a3b4-107">La función de devolución de llamada ya debe estar definido en la página web actual.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-107">The callback function must already be defined in the current Web page.</span></span> <span data-ttu-id="4a3b4-108">El tipo de contenido de una respuesta JSONP es `application/javascript`.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-108">The content type of a JSONP response is `application/javascript`.</span></span>

<span data-ttu-id="4a3b4-109">JSONP no está habilitado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-109">JSONP is not automatically enabled.</span></span> <span data-ttu-id="4a3b4-110">Para habilitarlo, establezca el atributo `javascriptCallbackEnabled` como `true` en uno de los extremos estándar HTTP (<xref:System.ServiceModel.Description.WebHttpEndpoint> o <xref:System.ServiceModel.Description.WebScriptEndpoint>), como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-110">To enable it, set the `javascriptCallbackEnabled` attribute to `true` on one of the HTTP standard endpoints (<xref:System.ServiceModel.Description.WebHttpEndpoint> or <xref:System.ServiceModel.Description.WebScriptEndpoint>), as shown in the following example.</span></span>

```xml
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint name="" javascriptCallbackEnabled="true"/>
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

<span data-ttu-id="4a3b4-111">El nombre de la función de devolución de llamada se puede especificar en una variable de consulta denominada devolución de llamada, tal y como se muestra en la siguiente dirección URL.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-111">The name of the callback function can be specified in a query variable called callback as shown in the following URL.</span></span>

`http://baseaddress/Service/RestService?callback=functionName`

<span data-ttu-id="4a3b4-112">Cuando se invoca, el servicio envía una respuesta como la siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-112">When invoked, the service sends a response like the following.</span></span>

```javascript
functionName({"root":"Something"});
```  

<span data-ttu-id="4a3b4-113">También puede especificar el nombre de la función de devolución de llamada aplicando <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute> a la clase de servicio, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-113">You can also specify the callback function name by applying the <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute> to the service class, as shown in the following example.</span></span>

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

<span data-ttu-id="4a3b4-114">En el servicio mostrado previamente, la solicitud tiene el aspecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-114">For the service shown previously, a request looks like the following.</span></span>

`http://baseaddress/Service/RestService?$callback=anotherFunction`

<span data-ttu-id="4a3b4-115">Cuando se invoca, el servicio responde del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-115">When invoked, the service responds with the following.</span></span>

```javascript
anotherFunction ({"root":"Something"});
```

## <a name="http-status-codes"></a><span data-ttu-id="4a3b4-116">Códigos de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="4a3b4-116">HTTP Status Codes</span></span>

<span data-ttu-id="4a3b4-117">Las respuestas JSONP con códigos de estado HTTP distintos de 200 incluyen un segundo parámetro con la representación numérica del código de estado HTTP, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-117">JSONP responses with HTTP status codes other than 200 include a second parameter with the numeric representation of the HTTP status code, as shown in the following example.</span></span>

```javascript
anotherFunction ({"root":"Something"}, 201);
```

## <a name="validations"></a><span data-ttu-id="4a3b4-118">Validaciones</span><span class="sxs-lookup"><span data-stu-id="4a3b4-118">Validations</span></span>

<span data-ttu-id="4a3b4-119">Se realizan las siguientes validaciones cuando JSONP está habilitado:</span><span class="sxs-lookup"><span data-stu-id="4a3b4-119">The following validations are performed when JSONP is enabled:</span></span>

- <span data-ttu-id="4a3b4-120">La infraestructura de WCF produce una excepción si `javascriptCallback` está habilitado, existe un parámetro de cadena de consulta de devolución de llamada en la solicitud, y el formato de la respuesta está establecido en JSON.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-120">The WCF infrastructure throws an exception if `javascriptCallback` is enabled, a callback query-string parameter is present in the request and the response format is set to JSON.</span></span>

- <span data-ttu-id="4a3b4-121">Si la solicitud contiene el parámetro de cadena de consulta de devolución de llamada, pero la operación no es un HTTP GET, se omite el parámetro de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-121">If the request contains the callback query string parameter but the operation is not an HTTP GET, the callback parameter is ignored.</span></span>

- <span data-ttu-id="4a3b4-122">Si el nombre de devolución de llamada es `null` o una cadena vacía, la respuesta no obtiene el formato JSONP.</span><span class="sxs-lookup"><span data-stu-id="4a3b4-122">If the callback name is `null` or empty string the response is not formatted as JSONP.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a3b4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a3b4-123">See also</span></span>

[<span data-ttu-id="4a3b4-124">Información general del modelo de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="4a3b4-124">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
