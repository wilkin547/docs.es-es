---
title: Procedimiento para hospedar un servicio WCF en IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 326a270c4af38738c910828acd483070ab02ecd1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593092"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="a9f1a-102">Procedimiento para hospedar un servicio WCF en IIS</span><span class="sxs-lookup"><span data-stu-id="a9f1a-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="a9f1a-103">En este tema se describen los pasos básicos necesarios para crear un servicio de Windows Communication Foundation (WCF) que se hospeda en Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="a9f1a-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="a9f1a-104">Este tema da por hecho que está familiarizado con IIS y sabe cómo usar la herramienta de administración de IIS para crear y administrar aplicaciones IIS.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="a9f1a-105">Para obtener más información acerca de IIS, vea [Internet Information Services](https://www.iis.net/).</span><span class="sxs-lookup"><span data-stu-id="a9f1a-105">For more information about IIS see [Internet Information Services](https://www.iis.net/).</span></span> <span data-ttu-id="a9f1a-106">Un servicio WCF que se ejecuta en el entorno de IIS saca el máximo partido de las características de IIS, como el reciclaje de procesos, el cierre por inactividad, la supervisión del estado de los procesos y la activación basada en mensajes.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="a9f1a-107">Esta opción de hospedaje requiere que se configure correctamente IIS, pero no requiere que se escriba ningún código de hospedaje como parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="a9f1a-108">Sólo puede utilizar el hospedaje de IIS con un transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="a9f1a-109">Para obtener más información sobre cómo interactúan WCF y ASP.NET, vea [servicios WCF y ASP.net](wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="a9f1a-109">For more information about how WCF and ASP.NET interact, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="a9f1a-110">Para obtener más información sobre la configuración de la seguridad, consulte [seguridad](security.md).</span><span class="sxs-lookup"><span data-stu-id="a9f1a-110">For more information about configuring security, see [Security](security.md).</span></span>  
  
 <span data-ttu-id="a9f1a-111">Para la copia de origen de este ejemplo, vea [hospedaje de IIS mediante código en línea](../samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="a9f1a-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="a9f1a-112">Para crear un servicio hospedado por IIS</span><span class="sxs-lookup"><span data-stu-id="a9f1a-112">To create a service hosted by IIS</span></span>  
  
1. <span data-ttu-id="a9f1a-113">Confirme que IIS está instalado y ejecutándose en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="a9f1a-114">Para obtener más información acerca de la instalación y configuración de IIS, vea [instalar y configurar iis 7,0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)</span><span class="sxs-lookup"><span data-stu-id="a9f1a-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)</span></span>  
  
2. <span data-ttu-id="a9f1a-115">Cree una nueva carpeta para los archivos de aplicación denominada "IISHostedCalcService", asegúrese de que ASP.NET tiene acceso al contenido de la carpeta y use la herramienta de administración de IIS para crear una nueva aplicación de IIS que se encuentre físicamente en este directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-115">Create a new folder for your application files called "IISHostedCalcService", ensure that ASP.NET has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="a9f1a-116">Cuando cree un alias para el directorio de la aplicación, use "IISHostedCalc".</span><span class="sxs-lookup"><span data-stu-id="a9f1a-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3. <span data-ttu-id="a9f1a-117">Cree un nuevo archivo denominado "service.svc" en el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="a9f1a-118">Edite este archivo agregando el @ServiceHost elemento siguiente.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
   ```
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. <span data-ttu-id="a9f1a-119">Cree un subdirectorio App_Code dentro del directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5. <span data-ttu-id="a9f1a-120">Cree un archivo de código denominado Service.cs en el subdirectorio App_Code.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6. <span data-ttu-id="a9f1a-121">Agregue las siguientes instrucciones using a la parte superior del archivo Service.cs.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. <span data-ttu-id="a9f1a-122">Agregue la declaración de espacio de nombres siguiente después de las instrucciones using.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. <span data-ttu-id="a9f1a-123">Defina el contrato de servicio dentro de la declaración de espacio de nombres, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="a9f1a-124">Implemente el contrato de servicio después de la definición de contrato de servicio, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="a9f1a-125">Cree un archivo denominado "Web.config" en el directorio de la aplicación y agregue el código de configuración siguiente a dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="a9f1a-126">En tiempo de ejecución, la infraestructura de WCF usa la información para construir un extremo con el que las aplicaciones cliente se pueden comunicar.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     <span data-ttu-id="a9f1a-127">Este ejemplo especifica puntos de conexión explícitamente en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="a9f1a-128">Si no agrega ningún punto de conexión al servicio, el tiempo de ejecución agregará los puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="a9f1a-129">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [configuración simplificada](../simplified-configuration.md) y [configuración simplificada de los servicios WCF](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a9f1a-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="a9f1a-130">Para asegurarse de que el servicio está hospedado correctamente, abra una instancia de Internet Explorer y vaya a la dirección URL del servicio: `http://localhost/IISHostedCalc/Service.svc`</span><span class="sxs-lookup"><span data-stu-id="a9f1a-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9f1a-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9f1a-131">Example</span></span>  
 <span data-ttu-id="a9f1a-132">A continuación, se muestra el código completo del servicio de calculadora hospedado en IIS.</span><span class="sxs-lookup"><span data-stu-id="a9f1a-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="a9f1a-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9f1a-133">See also</span></span>

- [<span data-ttu-id="a9f1a-134">Hospedaje en Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="a9f1a-134">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="a9f1a-135">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a9f1a-135">Hosting Services</span></span>](../hosting-services.md)
- [<span data-ttu-id="a9f1a-136">Servicios WCF y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9f1a-136">WCF Services and ASP.NET</span></span>](wcf-services-and-aspnet.md)
- [<span data-ttu-id="a9f1a-137">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a9f1a-137">Security</span></span>](security.md)
- <span data-ttu-id="a9f1a-138">[Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a9f1a-138">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
