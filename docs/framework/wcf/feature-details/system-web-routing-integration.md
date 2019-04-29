---
title: Integración de System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 3d5c3d7586189e0939fd52bc2b5feac51ae00613
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933892"
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="4e127-102">Integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="4e127-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="4e127-103">Al hospedar un servicio de Windows Communication Foundation (WCF) en servicios de Internet Information Server (IIS) se coloca un archivo .svc en el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="4e127-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="4e127-104">Este archivo .svc especifica el generador de host de servicio que se debe usar, así como la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="4e127-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="4e127-105">Al realizar solicitudes al servicio especificar el archivo .svc en el URI, por ejemplo: `http://contoso.com/EmployeeServce.svc`.</span><span class="sxs-lookup"><span data-stu-id="4e127-105">When making requests to the service you specify the .svc file in the URI, for example: `http://contoso.com/EmployeeServce.svc`.</span></span> <span data-ttu-id="4e127-106">Para programadores que escriben servicios de REST, este tipo de URI no es óptimo.</span><span class="sxs-lookup"><span data-stu-id="4e127-106">For programmers writing REST services this type of URI is not optimal.</span></span> <span data-ttu-id="4e127-107">Los URI para los servicios de REST especifican un recurso determinado y normalmente no tienen ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="4e127-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="4e127-108">El <xref:System.Web.Routing> característica de integración le permite hospedar un servicio WCF REST que responde a URI sin extensión.</span><span class="sxs-lookup"><span data-stu-id="4e127-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="4e127-109">Para obtener más información acerca de enrutamiento, consulte [enrutamiento ASP.NET](https://go.microsoft.com/fwlink/?LinkId=184660).</span><span class="sxs-lookup"><span data-stu-id="4e127-109">For more information about routing see [ASP.NET Routing](https://go.microsoft.com/fwlink/?LinkId=184660).</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="4e127-110">Usar la integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="4e127-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="4e127-111">Para usar la característica de integración de <xref:System.Web.Routing>, utilice la clase <xref:System.ServiceModel.Activation.ServiceRoute> para crear una o más rutas y agregarlas a <xref:System.Web.Routing.RouteTable> en un archivo Global.asax.</span><span class="sxs-lookup"><span data-stu-id="4e127-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="4e127-112">Estas rutas especifican los URI relativos a los que responde el servicio.</span><span class="sxs-lookup"><span data-stu-id="4e127-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="4e127-113">En el ejemplo siguiente se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="4e127-113">The following example shows how to do this.</span></span>  
  
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
  
 <span data-ttu-id="4e127-114">Esto enruta todas las solicitudes con un URI relativo que empiece por Customers (Clientes) al servicio `Service`.</span><span class="sxs-lookup"><span data-stu-id="4e127-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="4e127-115">En el archivo Web.config, debe agregar el módulo `System.Web.Routing.UrlRoutingModule`, establecer el atributo `runAllManagedModulesForAllRequests` como `true` y agregar el controlador `UrlRoutingHandler` al elemento `<system.webServer>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4e127-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="4e127-116">Esto carga un módulo y el controlador requerido para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="4e127-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="4e127-117">Para más información, vea [Enrutamiento](../../../../docs/framework/wcf/feature-details/routing.md).</span><span class="sxs-lookup"><span data-stu-id="4e127-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="4e127-118">También debe establecer el atributo `aspNetCompatibilityEnabled` como `true` en el elemento `<serviceHostingEnvironment>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4e127-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="4e127-119">La clase que implementa el servicio debe habilitar los requisitos de compatibilidad de ASP.NET, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4e127-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e127-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e127-120">See also</span></span>

- [<span data-ttu-id="4e127-121">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="4e127-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="4e127-122">Enrutamiento de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4e127-122">ASP.NET Routing</span></span>](https://go.microsoft.com/fwlink/?LinkId=184660)
