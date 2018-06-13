---
title: Procedimiento para hospedar un servicio WCF en IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: a1759434d259cdffe1dac6b19a6582bfb83784bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492490"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="5f6aa-102">Procedimiento para hospedar un servicio WCF en IIS</span><span class="sxs-lookup"><span data-stu-id="5f6aa-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="5f6aa-103">En este tema se describe los pasos básicos necesarios para crear un servicio de Windows Communication Foundation (WCF) que se hospeda en Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="5f6aa-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="5f6aa-104">Este tema da por hecho que está familiarizado con IIS y sabe cómo usar la herramienta de administración de IIS para crear y administrar aplicaciones IIS.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="5f6aa-105">Para obtener más información acerca de IIS, consulte [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span><span class="sxs-lookup"><span data-stu-id="5f6aa-105">For more information about IIS see [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="5f6aa-106">Un servicio WCF que se ejecuta en el entorno de IIS aprovecha al máximo las características IIS, como el reciclaje de procesos, cierre por inactividad, supervisión de estado de procesos y activación basada en mensajes.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="5f6aa-107">Esta opción de hospedaje requiere que se configure correctamente IIS, pero no requiere que se escriba ningún código de hospedaje como parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="5f6aa-108">Sólo puede utilizar el hospedaje de IIS con un transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="5f6aa-109">Para obtener más información acerca de cómo WCF y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interactuar, consulte [servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="5f6aa-109">For more information about how WCF and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="5f6aa-110">Para obtener más información sobre la configuración de seguridad, consulte [seguridad](../../../../docs/framework/wcf/feature-details/security.md).</span><span class="sxs-lookup"><span data-stu-id="5f6aa-110">For more information about configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="5f6aa-111">Para la copia de origen de este ejemplo, vea [IIS hospedaje mediante alineado código](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="5f6aa-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="5f6aa-112">Para crear un servicio hospedado por IIS</span><span class="sxs-lookup"><span data-stu-id="5f6aa-112">To create a service hosted by IIS</span></span>  
  
1.  <span data-ttu-id="5f6aa-113">Confirme que IIS está instalado y ejecutándose en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="5f6aa-114">Para obtener más información sobre la instalación y configuración de IIS, consulte [instalar y configurar IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="5f6aa-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2.  <span data-ttu-id="5f6aa-115">Cree una nueva carpeta para los archivos de la aplicación denominada "IISHostedCalcService", asegúrese de que [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] tiene acceso al contenido de la carpeta, y use la herramienta de administración de IIS para crear una nueva aplicación IIS que se ubique físicamente en este directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-115">Create a new folder for your application files called "IISHostedCalcService", ensure that [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="5f6aa-116">Cuando cree un alias para el directorio de la aplicación, use "IISHostedCalc".</span><span class="sxs-lookup"><span data-stu-id="5f6aa-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3.  <span data-ttu-id="5f6aa-117">Cree un nuevo archivo denominado "service.svc" en el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="5f6aa-118">Editar este archivo agregando las siguientes @ServiceHost elemento.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  <span data-ttu-id="5f6aa-119">Cree un subdirectorio App_Code dentro del directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5.  <span data-ttu-id="5f6aa-120">Cree un archivo de código denominado Service.cs en el subdirectorio App_Code.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6.  <span data-ttu-id="5f6aa-121">Agregue las siguientes instrucciones using a la parte superior del archivo Service.cs.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  <span data-ttu-id="5f6aa-122">Agregue la declaración de espacio de nombres siguiente después de las instrucciones using.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  <span data-ttu-id="5f6aa-123">Defina el contrato de servicio dentro de la declaración de espacio de nombres, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="5f6aa-124">Implemente el contrato de servicio después de la definición de contrato de servicio, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="5f6aa-125">Cree un archivo denominado "Web.config" en el directorio de la aplicación y agregue el código de configuración siguiente a dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="5f6aa-126">En tiempo de ejecución, la infraestructura de WCF usa la información para construir un punto de conexión que las aplicaciones cliente pueden comunicarse con.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="5f6aa-127">Este ejemplo especifica puntos de conexión explícitamente en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="5f6aa-128">Si no agrega ningún punto de conexión al servicio, el tiempo de ejecución agregará los puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="5f6aa-129">Para obtener más información acerca de los puntos de conexión de forma predeterminada, los enlaces y comportamientos vea [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="5f6aa-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="5f6aa-130">Para asegurarse de que el servicio está hospedado correctamente, abra una instancia de Internet Explorer y vaya a la dirección URL del servicio: `http://localhost/IISHostedCalc/Service.svc`</span><span class="sxs-lookup"><span data-stu-id="5f6aa-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f6aa-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5f6aa-131">Example</span></span>  
 <span data-ttu-id="5f6aa-132">A continuación, se muestra el código completo del servicio de calculadora hospedado en IIS.</span><span class="sxs-lookup"><span data-stu-id="5f6aa-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="5f6aa-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f6aa-133">See Also</span></span>  
 [<span data-ttu-id="5f6aa-134">Hospedaje en Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="5f6aa-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="5f6aa-135">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5f6aa-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="5f6aa-136">Servicios WCF y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5f6aa-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [<span data-ttu-id="5f6aa-137">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5f6aa-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
 [<span data-ttu-id="5f6aa-138">Características de hospedaje de Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="5f6aa-138">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
