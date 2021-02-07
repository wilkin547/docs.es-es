---
description: 'Más información acerca de: servicio AJAX básico'
title: Servicio AJAX básico
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: 08670c0e87a6f258d29288e2072cd04dd875088a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732727"
---
# <a name="basic-ajax-service"></a>Servicio AJAX básico

En este ejemplo se muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio JavaScript y XML (AJAX) ASP.NET asincrónico básico (un servicio al que se puede tener acceso mediante código JavaScript desde un cliente del explorador Web). El servicio utiliza el atributo <xref:System.ServiceModel.Web.WebGetAttribute> para asegurarse de que el servicio responde a las solicitudes HTTP GET y de que está configurado para utilizar el formato de datos de Notación de objeto de JavaScript (JSON) para las respuestas.

La compatibilidad de AJAX en WCF está optimizada para su uso con ASP.NET AJAX a través del `ScriptManager` control. Para obtener un ejemplo del uso de WCF con ASP.NET AJAX, consulte los [ejemplos de Ajax](ajax.md).

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

En el código siguiente, el atributo <xref:System.ServiceModel.Web.WebGetAttribute> se aplica a la operación `Add` para asegurarse de que el servicio responde a las solicitudes HTTP GET. El código usa GET por simplicidad (puede construir una solicitud HTTP GET desde cualquier explorador web). También puede utilizar GET para habilitar el almacenamiento en caché. HTTP POST es el valor predeterminado en la ausencia del atributo `WebGetAttribute`.

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

El archivo .svc de ejemplo utiliza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, que agrega un punto de conexión estándar <xref:System.ServiceModel.Description.WebScriptEndpoint> al servicio. El extremo se configura en una dirección vacía relativa al archivo .svc. Esto significa que la dirección del servicio es `http://localhost/ServiceModelSamples/service.svc` , sin sufijos adicionales que no sean el nombre de la operación.

`<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>`

<xref:System.ServiceModel.Description.WebScriptEndpoint> se preconfigura de modo que el servicio esté accesible desde una página de cliente AJAX de ASP.NET. La siguiente sección de Web.config se puede utilizar para realizar cambios de configuración adicionales en el punto de conexión. Se puede quitar si no se necesita ningún cambio adicional.

```xml
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <!-- Use this element to configure the endpoint -->
      <standardEndpoint name=""  />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

<xref:System.ServiceModel.Description.WebScriptEndpoint> establece el formato de datos predeterminado para el servicio en JSON en lugar de XML. Para invocar el servicio, vaya a `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` después de completar los pasos de configuración y compilación que se muestran más adelante en este tema. El uso de una solicitud HTTP GET habilita esta funcionalidad de la prueba.

La página web del cliente SimpleAjaxClientPage.aspx contiene el código de ASP.NET para invocar el servicio siempre que el usuario haga clic en uno de los botones de operación en la página. El control `ScriptManager` se utiliza para hacer que un proxy al servicio sea accesible a través de JavaScript.

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">
    <Services>
        <asp:ServiceReference Path="service.svc" />
    </Services>
</asp:ScriptManager>
```

Se crean instancias del proxy local y las operaciones se invocan utilizando el siguiente código de JavaScript.

```javascript
// Code for extracting arguments n1 and n2 omitted…
// Instantiate a service proxy
var proxy = new SimpleAjaxService.ICalculator();
// Code for selecting operation omitted…
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);
```

Si la llamada del servicio es correcta, el código invoca el controlador `onSuccess` y el resultado de la operación se muestra en un cuadro de texto.

```javascript
function onSuccess(mathResult){
     document.getElementById("result").value = mathResult;
}
```

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`
