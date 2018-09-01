---
title: Desarrollar aplicaciones de servicios de Windows
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: 2c7fb148b96d5ff9804bcb0bb7c842c475c0f117
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385986"
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="da0f3-102">Desarrollar aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="da0f3-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="da0f3-103">Con Microsoft Visual Studio o el SDK de Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], puede crear fácilmente servicios mediante la creación de una aplicación que se instale como un servicio.</span><span class="sxs-lookup"><span data-stu-id="da0f3-103">Using Microsoft Visual Studio or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="da0f3-104">Este tipo de aplicación se denomina servicio Windows.</span><span class="sxs-lookup"><span data-stu-id="da0f3-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="da0f3-105">Con las características de la plataforma, puede crear servicios, instalarlos e iniciar, detener y controlar su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="da0f3-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="da0f3-106">La plantilla de servicio de Windows para C++ no se ha incluido en Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="da0f3-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="da0f3-107">Para crear un servicio de Windows, puede crear un servicio en código administrado en Visual C# o Visual Basic, que podría interoperar con el código C++ existente si es necesario, o bien puede crear un servicio de Windows en C++ nativo mediante el [Asistente para proyectos ATL](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="da0f3-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da0f3-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="da0f3-108">In This Section</span></span>  
 [<span data-ttu-id="da0f3-109">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="da0f3-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="da0f3-110">Proporciona información general de las aplicaciones de servicio de Windows, la duración de un servicio y las diferencias entre las aplicaciones de servicio y otros tipos de proyectos comunes.</span><span class="sxs-lookup"><span data-stu-id="da0f3-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="da0f3-111">Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes</span><span class="sxs-lookup"><span data-stu-id="da0f3-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="da0f3-112">Proporciona un ejemplo de cómo crear un servicio en Visual Basic y Visual C#.</span><span class="sxs-lookup"><span data-stu-id="da0f3-112">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>  
  
 [<span data-ttu-id="da0f3-113">Arquitectura de programación de aplicaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="da0f3-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="da0f3-114">Explica los elementos del lenguaje utilizados en la programación de servicios.</span><span class="sxs-lookup"><span data-stu-id="da0f3-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="da0f3-115">Creación de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="da0f3-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="da0f3-116">Describe el proceso de creación y configuración de servicios de Windows mediante la plantilla de proyecto de servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="da0f3-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da0f3-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="da0f3-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="da0f3-118">Describe las características principales de la clase <xref:System.ServiceProcess.ServiceBase>, que se utiliza para crear servicios.</span><span class="sxs-lookup"><span data-stu-id="da0f3-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="da0f3-119">Describe las características de la clase <xref:System.ServiceProcess.ServiceProcessInstaller>, que se utiliza junto con la clase <xref:System.ServiceProcess.ServiceInstaller> para instalar y desinstalar servicios.</span><span class="sxs-lookup"><span data-stu-id="da0f3-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="da0f3-120">Describe las características de la clase <xref:System.ServiceProcess.ServiceInstaller>, que se utiliza junto con la clase <xref:System.ServiceProcess.ServiceProcessInstaller> para instalar y desinstalar su servicio.</span><span class="sxs-lookup"><span data-stu-id="da0f3-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="da0f3-121">NIB: Crear proyectos a partir de plantillas</span><span class="sxs-lookup"><span data-stu-id="da0f3-121">NIB Creating Projects from Templates</span></span>](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="da0f3-122">Describe los tipos de proyectos utilizados en este capítulo y cómo elegir entre ellos.</span><span class="sxs-lookup"><span data-stu-id="da0f3-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
