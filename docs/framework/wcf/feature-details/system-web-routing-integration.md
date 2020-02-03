---
title: Integración de System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: fdc355d4560294a16f3e9c488fdaf142d2982c0d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745342"
---
# <a name="systemwebrouting-integration"></a>Integración de System.Web.Routing
Al hospedar un servicio de Windows Communication Foundation (WCF) en Internet Information Services (IIS), se coloca un archivo. SVC en el directorio virtual. Este archivo .svc especifica el generador de host de servicio que se debe usar, así como la clase que implementa el servicio. Al hacer solicitudes al servicio, se especifica el archivo. SVC en el URI, por ejemplo: `http://contoso.com/EmployeeServce.svc`. Para programadores que escriben servicios de REST, este tipo de URI no es óptimo. Los URI para los servicios de REST especifican un recurso determinado y normalmente no tienen ninguna extensión. La característica de integración de <xref:System.Web.Routing> permite hospedar un servicio REST de WCF que responde a los URI sin una extensión. Para obtener más información acerca del enrutamiento, consulte [enrutamiento ASP.net](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100)).  
  
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
- [Enrutamiento ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))
