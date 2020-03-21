---
title: Integración de System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: a80b5c3b336b4fd18b347a25ceaf509baf6461b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184395"
---
# <a name="systemwebrouting-integration"></a>Integración de System.Web.Routing
Al hospedar un servicio de Windows Communication Foundation (WCF) en Internet Information Service (IIS) se coloca un archivo .svc en el directorio virtual. Este archivo .svc especifica el generador de host de servicio que se debe usar, así como la clase que implementa el servicio. Al realizar solicitudes al servicio, especifique el archivo .svc `http://contoso.com/EmployeeServce.svc`en el URI, por ejemplo: . Para programadores que escriben servicios de REST, este tipo de URI no es óptimo. Los URI para los servicios de REST especifican un recurso determinado y normalmente no tienen ninguna extensión. La <xref:System.Web.Routing> característica de integración le permite hospedar un servicio REST de WCF que responde a los URI sin una extensión. Para obtener más información sobre el [enrutamiento,](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))consulte enrutamiento ASP.NET .  
  
## <a name="using-systemwebrouting-integration"></a>Usar la integración de System.Web.Routing  
 Para usar la característica de integración de <xref:System.Web.Routing>, utilice la clase <xref:System.ServiceModel.Activation.ServiceRoute> para crear una o más rutas y agregarlas a <xref:System.Web.Routing.RouteTable> en un archivo Global.asax. Estas rutas especifican los URI relativos a los que responde el servicio. El ejemplo siguiente muestra cómo hacerlo.  
  
```aspx-csharp  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));
   }  
</script>  
```  
  
 Esto enruta todas las solicitudes con un URI relativo que empiece por Customers (Clientes) al servicio `Service`.  
  
 En el archivo Web.config, debe agregar el módulo `System.Web.Routing.UrlRoutingModule`, establecer el atributo `runAllManagedModulesForAllRequests` como `true` y agregar el controlador `UrlRoutingHandler` al elemento `<system.webServer>`, tal y como se muestra en el siguiente ejemplo.  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 Esto carga un módulo y el controlador requerido para el enrutamiento. Para más información, vea [Enrutamiento](../../../../docs/framework/wcf/feature-details/routing.md). También debe establecer el atributo `aspNetCompatibilityEnabled` como `true` en el elemento `<serviceHostingEnvironment>`, tal y como se muestra en el siguiente ejemplo.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 La clase que implementa el servicio debe habilitar los requisitos de compatibilidad de ASP.NET, tal y como se muestra en el siguiente ejemplo.  
  
```csharp
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a>Consulte también

- [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [Enrutamiento de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))
