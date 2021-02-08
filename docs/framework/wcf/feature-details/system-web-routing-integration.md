---
description: 'Más información sobre: System. Web. Routing Integration'
title: Integración de System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 8f396d5a3cad30f5cc67cb0cf44fad76a0bb54c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793342"
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="76d46-103">Integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="76d46-103">System.Web.Routing Integration</span></span>

<span data-ttu-id="76d46-104">Al hospedar un servicio de Windows Communication Foundation (WCF) en Internet Information Services (IIS), se coloca un archivo. SVC en el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="76d46-104">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="76d46-105">Este archivo .svc especifica el generador de host de servicio que se debe usar, así como la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="76d46-105">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="76d46-106">Al hacer solicitudes al servicio, se especifica el archivo. SVC en el URI, por ejemplo: `http://contoso.com/EmployeeServce.svc` .</span><span class="sxs-lookup"><span data-stu-id="76d46-106">When making requests to the service you specify the .svc file in the URI, for example: `http://contoso.com/EmployeeServce.svc`.</span></span> <span data-ttu-id="76d46-107">Para programadores que escriben servicios de REST, este tipo de URI no es óptimo.</span><span class="sxs-lookup"><span data-stu-id="76d46-107">For programmers writing REST services, this type of URI is not optimal.</span></span> <span data-ttu-id="76d46-108">Los URI para los servicios de REST especifican un recurso determinado y normalmente no tienen ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="76d46-108">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="76d46-109">La <xref:System.Web.Routing> característica de integración de permite hospedar un servicio REST de WCF que responde a los URI sin una extensión.</span><span class="sxs-lookup"><span data-stu-id="76d46-109">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="76d46-110">Para obtener más información acerca del enrutamiento, consulte [enrutamiento ASP.net](/previous-versions/aspnet/cc668201(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="76d46-110">For more information about routing see [ASP.NET Routing](/previous-versions/aspnet/cc668201(v=vs.100)).</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="76d46-111">Usar la integración de System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="76d46-111">Using System.Web.Routing Integration</span></span>  

 <span data-ttu-id="76d46-112">Para usar la característica de integración de <xref:System.Web.Routing>, utilice la clase <xref:System.ServiceModel.Activation.ServiceRoute> para crear una o más rutas y agregarlas a <xref:System.Web.Routing.RouteTable> en un archivo Global.asax.</span><span class="sxs-lookup"><span data-stu-id="76d46-112">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="76d46-113">Estas rutas especifican los URI relativos a los que responde el servicio.</span><span class="sxs-lookup"><span data-stu-id="76d46-113">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="76d46-114">El ejemplo siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="76d46-114">The following example shows how to do this.</span></span>  
  
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
  
 <span data-ttu-id="76d46-115">Esto enruta todas las solicitudes con un URI relativo que empiece por Customers (Clientes) al servicio `Service`.</span><span class="sxs-lookup"><span data-stu-id="76d46-115">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="76d46-116">En el archivo Web.config, debe agregar el módulo `System.Web.Routing.UrlRoutingModule`, establecer el atributo `runAllManagedModulesForAllRequests` como `true` y agregar el controlador `UrlRoutingHandler` al elemento `<system.webServer>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="76d46-116">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="76d46-117">Esto carga un módulo y el controlador requerido para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="76d46-117">This loads a module and handler required for routing.</span></span> <span data-ttu-id="76d46-118">Para más información, vea [Enrutamiento](routing.md).</span><span class="sxs-lookup"><span data-stu-id="76d46-118">For more information, see [Routing](routing.md).</span></span> <span data-ttu-id="76d46-119">También debe establecer el atributo `aspNetCompatibilityEnabled` como `true` en el elemento `<serviceHostingEnvironment>`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="76d46-119">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="76d46-120">La clase que implementa el servicio debe habilitar los requisitos de compatibilidad de ASP.NET, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="76d46-120">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```csharp
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="76d46-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="76d46-121">See also</span></span>

- [<span data-ttu-id="76d46-122">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="76d46-122">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- <span data-ttu-id="76d46-123">[Enrutamiento de ASP.NET](/previous-versions/aspnet/cc668201(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="76d46-123">[ASP.NET Routing](/previous-versions/aspnet/cc668201(v=vs.100))</span></span>
