---
title: Desarrollar aplicaciones de servicios de Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 2912568e967c8c6096842b1b4f24eac88318dffb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="241b6-102">Desarrollar aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="241b6-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="241b6-103">Mediante Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, puede crear fácilmente servicios mediante la creación de una aplicación que se instala como un servicio.</span><span class="sxs-lookup"><span data-stu-id="241b6-103">Using Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="241b6-104">Este tipo de aplicación se denomina un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="241b6-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="241b6-105">Características del marco de trabajo, puede crear servicios, instalarlos e iniciar, detener y controlar su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="241b6-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="241b6-106">La plantilla de servicio de Windows de C++ no se incluyó en Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="241b6-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="241b6-107">Para crear un servicio de Windows, puede crear un servicio en código administrado en Visual C# o Visual Basic, que puede interactuar con el código de C++ existente si es necesario, o puede crear un servicio de Windows en C++ nativo mediante el [Asistente para proyectos de ATL](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="241b6-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="241b6-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="241b6-108">In This Section</span></span>  
 [<span data-ttu-id="241b6-109">Introducción a las aplicaciones de servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="241b6-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="241b6-110">Proporciona información general de las aplicaciones de servicio de Windows, la duración de un servicio, y cómo las aplicaciones de servicio se diferencian de otros tipos de proyecto comunes.</span><span class="sxs-lookup"><span data-stu-id="241b6-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="241b6-111">Tutorial: Crear una aplicación de servicio de Windows en el Diseñador de componentes</span><span class="sxs-lookup"><span data-stu-id="241b6-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="241b6-112">Proporciona un ejemplo de creación de un servicio en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] y Visual C#.</span><span class="sxs-lookup"><span data-stu-id="241b6-112">Provides an example of creating a service in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] and Visual C#.</span></span>  
  
 [<span data-ttu-id="241b6-113">Arquitectura de programación de aplicaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="241b6-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="241b6-114">Explica los elementos de lenguaje que se utilizan en la programación de servicio.</span><span class="sxs-lookup"><span data-stu-id="241b6-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="241b6-115">Cómo: crear servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="241b6-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="241b6-116">Describe el proceso de creación y configuración de servicios de Windows mediante la plantilla de proyecto de servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="241b6-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="241b6-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="241b6-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="241b6-118">Describe las características principales de la <xref:System.ServiceProcess.ServiceBase> (clase), que se utiliza para crear servicios.</span><span class="sxs-lookup"><span data-stu-id="241b6-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="241b6-119">Describe las características de la <xref:System.ServiceProcess.ServiceProcessInstaller> (clase), que se utiliza junto con la <xref:System.ServiceProcess.ServiceInstaller> clase para instalar y desinstalar servicios.</span><span class="sxs-lookup"><span data-stu-id="241b6-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="241b6-120">Describe las características de la <xref:System.ServiceProcess.ServiceInstaller> (clase), que se utiliza junto con la <xref:System.ServiceProcess.ServiceProcessInstaller> clase para instalar y desinstalar el servicio.</span><span class="sxs-lookup"><span data-stu-id="241b6-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="241b6-121">NIB crear proyectos a partir de plantillas</span><span class="sxs-lookup"><span data-stu-id="241b6-121">NIB Creating Projects from Templates</span></span>](http://msdn.microsoft.com/en-us/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="241b6-122">Describe los proyectos de tipos utilizados en este capítulo y cómo elegir entre ellos.</span><span class="sxs-lookup"><span data-stu-id="241b6-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
