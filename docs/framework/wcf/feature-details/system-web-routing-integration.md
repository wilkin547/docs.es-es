---
title: Integración de System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 059f14c94bb7502a2e4f4616ca2c5e6ac5273afa
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600742"
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="19294-102">Integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="19294-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="19294-103">Al hospedar un servicio de Windows Communication Foundation (WCF) en Internet Information Services (IIS), se coloca un archivo. SVC en el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="19294-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="19294-104">Este archivo .svc especifica el generador de host de servicio que se debe usar, así como la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="19294-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="19294-105">Al hacer solicitudes al servicio, se especifica el archivo. SVC en el URI, por ejemplo: `http://contoso.com/EmployeeServce.svc` .</span><span class="sxs-lookup"><span data-stu-id="19294-105">When making requests to the service you specify the .svc file in the URI, for example: `http://contoso.com/EmployeeServce.svc`.</span></span> <span data-ttu-id="19294-106">Para programadores que escriben servicios de REST, este tipo de URI no es óptimo.</span><span class="sxs-lookup"><span data-stu-id="19294-106">For programmers writing REST services, this type of URI is not optimal.</span></span> <span data-ttu-id="19294-107">Los URI para los servicios de REST especifican un recurso determinado y normalmente no tienen ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="19294-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="19294-108">La <xref:System.Web.Routing> característica de integración de permite hospedar un servicio REST de WCF que responde a los URI sin una extensión.</span><span class="sxs-lookup"><span data-stu-id="19294-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="19294-109">Para obtener más información acerca del enrutamiento, consulte [enrutamiento ASP.net](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="19294-109">For more information about routing see [ASP.NET Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100)).</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="19294-110">Usar la integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="19294-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="19294-111">Para usar la característica de integración de <xref:System.Web.Routing>, utilice la clase <xref:System.ServiceModel.Activation.ServiceRoute> para crear una o más rutas y agregarlas a <xref:System.Web.Routing.RouteTable> en un archivo Global.asax.</span><span class="sxs-lookup"><span data-stu-id="19294-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="19294-112">Estas rutas especifican los URI relativos a los que responde el servicio.</span><span class="sxs-lookup"><span data-stu-id="19294-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="19294-113">El ejemplo siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="19294-113">The following example shows how to do this.</span></span>  
  
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
  
 <span data-ttu-id="19294-114">Esto enruta todas las solicitudes con un URI relativo que empiece por Customers (Clientes) al servicio `Service`.</span><span class="sxs-lookup"><span data-stu-id="19294-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="19294-115">En el archivo Web.config, debe agregar el módulo `System.Web.Routing.UrlRoutingModule`, establecer el atributo `runAllManagedModulesForAllRequests` como `true` y agregar el controlador `UrlRoutingHandler` al elemento `<system.webServer>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="19294-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="19294-116">Esto carga un módulo y el controlador requerido para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="19294-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="19294-117">Para más información, vea [Enrutamiento](routing.md).</span><span class="sxs-lookup"><span data-stu-id="19294-117">For more information, see [Routing](routing.md).</span></span> <span data-ttu-id="19294-118">También debe establecer el atributo `aspNetCompatibilityEnabled` como `true` en el elemento `<serviceHostingEnvironment>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="19294-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="19294-119">La clase que implementa el servicio debe habilitar los requisitos de compatibilidad de ASP.NET, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="19294-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```csharp
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="19294-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="19294-120">See also</span></span>

- [<span data-ttu-id="19294-121">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="19294-121">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- <span data-ttu-id="19294-122">[Enrutamiento de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="19294-122">[ASP.NET Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))</span></span>
