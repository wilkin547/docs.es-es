---
title: Integración de System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 3b95b3117941ce7d019b87b00181b2cbac652f43
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2018
ms.locfileid: "49308213"
---
# <a name="systemwebrouting-integration"></a>Integración de System.Web.Routing
Al hospedar un servicio de Windows Communication Foundation (WCF) en servicios de Internet Information Server (IIS) se coloca un archivo .svc en el directorio virtual. Este archivo .svc especifica el generador de host de servicio que se debe usar, así como la clase que implementa el servicio. Al realizar solicitudes al servicio especificar el archivo .svc en el URI, por ejemplo: `http://contoso.com/EmployeeServce.svc`. Para programadores que escriben servicios de REST, este tipo de URI no es óptimo. Los URI para los servicios de REST especifican un recurso determinado y normalmente no tienen ninguna extensión. El <xref:System.Web.Routing> característica de integración le permite hospedar un servicio WCF REST que responde a URI sin extensión. Para obtener más información acerca de enrutamiento, consulte [enrutamiento ASP.NET](https://go.microsoft.com/fwlink/?LinkId=184660).  
  
## <a name="using-systemwebrouting-integration"></a>Usar la integración de System.Web.Routing  
 Para usar la característica de integración de <xref:System.Web.Routing>, utilice la clase <xref:System.ServiceModel.Activation.ServiceRoute> para crear una o más rutas y agregarlas a <xref:System.Web.Routing.RouteTable> en un archivo Global.asax. Estas rutas especifican los URI relativos a los que responde el servicio. En el ejemplo siguiente se muestra cómo hacerlo.  
  
```  
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
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a>Vea también  
 [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Enrutamiento de ASP.NET](https://go.microsoft.com/fwlink/?LinkId=184660)
