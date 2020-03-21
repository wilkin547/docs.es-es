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
# <a name="systemwebrouting-integration"></a><span data-ttu-id="da800-102">Integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="da800-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="da800-103">Al hospedar un servicio de Windows Communication Foundation (WCF) en Internet Information Service (IIS) se coloca un archivo .svc en el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="da800-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="da800-104">Este archivo .svc especifica el generador de host de servicio que se debe usar, así como la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="da800-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="da800-105">Al realizar solicitudes al servicio, especifique el archivo .svc `http://contoso.com/EmployeeServce.svc`en el URI, por ejemplo: .</span><span class="sxs-lookup"><span data-stu-id="da800-105">When making requests to the service you specify the .svc file in the URI, for example: `http://contoso.com/EmployeeServce.svc`.</span></span> <span data-ttu-id="da800-106">Para programadores que escriben servicios de REST, este tipo de URI no es óptimo.</span><span class="sxs-lookup"><span data-stu-id="da800-106">For programmers writing REST services, this type of URI is not optimal.</span></span> <span data-ttu-id="da800-107">Los URI para los servicios de REST especifican un recurso determinado y normalmente no tienen ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="da800-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="da800-108">La <xref:System.Web.Routing> característica de integración le permite hospedar un servicio REST de WCF que responde a los URI sin una extensión.</span><span class="sxs-lookup"><span data-stu-id="da800-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="da800-109">Para obtener más información sobre el [enrutamiento,](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))consulte enrutamiento ASP.NET .</span><span class="sxs-lookup"><span data-stu-id="da800-109">For more information about routing see [ASP.NET Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100)).</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="da800-110">Usar la integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="da800-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="da800-111">Para usar la característica de integración de <xref:System.Web.Routing>, utilice la clase <xref:System.ServiceModel.Activation.ServiceRoute> para crear una o más rutas y agregarlas a <xref:System.Web.Routing.RouteTable> en un archivo Global.asax.</span><span class="sxs-lookup"><span data-stu-id="da800-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="da800-112">Estas rutas especifican los URI relativos a los que responde el servicio.</span><span class="sxs-lookup"><span data-stu-id="da800-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="da800-113">El ejemplo siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="da800-113">The following example shows how to do this.</span></span>  
  
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
  
 <span data-ttu-id="da800-114">Esto enruta todas las solicitudes con un URI relativo que empiece por Customers (Clientes) al servicio `Service`.</span><span class="sxs-lookup"><span data-stu-id="da800-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="da800-115">En el archivo Web.config, debe agregar el módulo `System.Web.Routing.UrlRoutingModule`, establecer el atributo `runAllManagedModulesForAllRequests` como `true` y agregar el controlador `UrlRoutingHandler` al elemento `<system.webServer>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="da800-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="da800-116">Esto carga un módulo y el controlador requerido para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="da800-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="da800-117">Para más información, vea [Enrutamiento](../../../../docs/framework/wcf/feature-details/routing.md).</span><span class="sxs-lookup"><span data-stu-id="da800-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="da800-118">También debe establecer el atributo `aspNetCompatibilityEnabled` como `true` en el elemento `<serviceHostingEnvironment>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="da800-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="da800-119">La clase que implementa el servicio debe habilitar los requisitos de compatibilidad de ASP.NET, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="da800-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```csharp
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="da800-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da800-120">See also</span></span>

- [<span data-ttu-id="da800-121">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="da800-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- <span data-ttu-id="da800-122">[Enrutamiento de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="da800-122">[ASP.NET Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))</span></span>
