---
title: Integración de System.Web.Routing
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 72403671fe6700ae26cae4471a1d0ac100005f3a
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="b46be-102">Integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="b46be-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="b46be-103">Al hospedar un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en Internet Information Service (IIS), se coloca un archivo .svc en el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="b46be-103">When hosting a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="b46be-104">Este archivo .svc especifica el generador de host de servicio que se debe usar, así como la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="b46be-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="b46be-105">Al realizar solicitudes al servicio de especificar el archivo .svc en el URI, por ejemplo: http://contoso.com/EmployeeServce.svc.</span><span class="sxs-lookup"><span data-stu-id="b46be-105">When making requests to the service you specify the .svc file in the URI, for example: http://contoso.com/EmployeeServce.svc.</span></span> <span data-ttu-id="b46be-106">Para programadores que escriben servicios de REST, este tipo de URI no es óptimo.</span><span class="sxs-lookup"><span data-stu-id="b46be-106">For programmers writing REST services this type of URI is not optimal.</span></span> <span data-ttu-id="b46be-107">Los URI para los servicios de REST especifican un recurso determinado y normalmente no tienen ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="b46be-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="b46be-108">La característica de integración <xref:System.Web.Routing> le permite hospedar un servicio de REST de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que responde a URI sin extensión.</span><span class="sxs-lookup"><span data-stu-id="b46be-108">The <xref:System.Web.Routing> integration feature allows you to host a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="b46be-109">Para obtener más información sobre enrutamiento, consulte [el enrutamiento de ASP.NET](http://go.microsoft.com/fwlink/?LinkId=184660) y [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b46be-109">For more information about routing see [ASP.NET Routing](http://go.microsoft.com/fwlink/?LinkId=184660) and the [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) sample.</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="b46be-110">Usar la integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="b46be-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="b46be-111">Para usar la característica de integración de <xref:System.Web.Routing>, utilice la clase <xref:System.ServiceModel.Activation.ServiceRoute> para crear una o más rutas y agregarlas a <xref:System.Web.Routing.RouteTable> en un archivo Global.asax.</span><span class="sxs-lookup"><span data-stu-id="b46be-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="b46be-112">Estas rutas especifican los URI relativos a los que responde el servicio.</span><span class="sxs-lookup"><span data-stu-id="b46be-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="b46be-113">En el ejemplo siguiente se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="b46be-113">The following example shows how to do this.</span></span>  
  
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
  
 <span data-ttu-id="b46be-114">Esto enruta todas las solicitudes con un URI relativo que empiece por Customers (Clientes) al servicio `Service`.</span><span class="sxs-lookup"><span data-stu-id="b46be-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="b46be-115">En el archivo Web.config, debe agregar el módulo `System.Web.Routing.UrlRoutingModule`, establecer el atributo `runAllManagedModulesForAllRequests` como `true` y agregar el controlador `UrlRoutingHandler` al elemento `<system.webServer>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b46be-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="b46be-116">Esto carga un módulo y el controlador requerido para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="b46be-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="b46be-117">Para más información, vea [Enrutamiento](../../../../docs/framework/wcf/feature-details/routing.md).</span><span class="sxs-lookup"><span data-stu-id="b46be-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="b46be-118">También debe establecer el atributo `aspNetCompatibilityEnabled` como `true` en el elemento `<serviceHostingEnvironment>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b46be-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="b46be-119">La clase que implementa el servicio debe habilitar los requisitos de compatibilidad de ASP.NET, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b46be-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="b46be-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b46be-120">See Also</span></span>  
 [<span data-ttu-id="b46be-121">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="b46be-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="b46be-122">Enrutamiento de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b46be-122">ASP.NET Routing</span></span>](http://go.microsoft.com/fwlink/?LinkId=184660)
