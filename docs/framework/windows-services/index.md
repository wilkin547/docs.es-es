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
ms.openlocfilehash: 61f969c22ac06bd6ed20ccfa9124db3bb35d0692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71053539"
---
# <a name="develop-windows-service-apps"></a><span data-ttu-id="475ec-102">Desarrollar aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="475ec-102">Develop Windows service apps</span></span>

<span data-ttu-id="475ec-103">Con Visual Studio o el SDK de .NET Framework, puede crear fácilmente servicios mediante la creación de una aplicación que se instale como un servicio.</span><span class="sxs-lookup"><span data-stu-id="475ec-103">Using Visual Studio or the .NET Framework SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="475ec-104">Este tipo de aplicación se denomina servicio Windows.</span><span class="sxs-lookup"><span data-stu-id="475ec-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="475ec-105">Con las características de la plataforma, puede crear servicios, instalarlos e iniciar, detener y controlar su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="475ec-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="475ec-106">En Visual Studio puede crear un servicio en código administrado en Visual C# o Visual Basic, que pueda interoperar con código C++ existente si es necesario.</span><span class="sxs-lookup"><span data-stu-id="475ec-106">In Visual Studio you can create a service in managed code in Visual C# or Visual Basic, which can interoperate with existing C++ code if required.</span></span> <span data-ttu-id="475ec-107">O bien, puede crear un servicio de Windows en C++ nativo mediante el [Asistente para proyectos ATL](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="475ec-107">Or, you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="475ec-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="475ec-108">In this section</span></span>

[<span data-ttu-id="475ec-109">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="475ec-109">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)

<span data-ttu-id="475ec-110">Proporciona información general de las aplicaciones de servicio de Windows, la duración de un servicio y las diferencias entre las aplicaciones de servicio y otros tipos de proyectos comunes.</span><span class="sxs-lookup"><span data-stu-id="475ec-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>

[<span data-ttu-id="475ec-111">Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes</span><span class="sxs-lookup"><span data-stu-id="475ec-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

<span data-ttu-id="475ec-112">Proporciona un ejemplo de cómo crear un servicio en Visual Basic y Visual C#.</span><span class="sxs-lookup"><span data-stu-id="475ec-112">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>

[<span data-ttu-id="475ec-113">Arquitectura de programación de aplicaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="475ec-113">Service Application Programming Architecture</span></span>](service-application-programming-architecture.md)

<span data-ttu-id="475ec-114">Explica los elementos del lenguaje utilizados en la programación de servicios.</span><span class="sxs-lookup"><span data-stu-id="475ec-114">Explains the language elements used in service programming.</span></span>

[<span data-ttu-id="475ec-115">Creación de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="475ec-115">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)

<span data-ttu-id="475ec-116">Describe el proceso de creación y configuración de servicios de Windows mediante la plantilla de proyecto de servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="475ec-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>

## <a name="related-sections"></a><span data-ttu-id="475ec-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="475ec-117">Related sections</span></span>

<span data-ttu-id="475ec-118"><xref:System.ServiceProcess.ServiceBase>: describe las características principales de la clase <xref:System.ServiceProcess.ServiceBase>, que se utiliza para crear servicios.</span><span class="sxs-lookup"><span data-stu-id="475ec-118"><xref:System.ServiceProcess.ServiceBase> - Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>

<span data-ttu-id="475ec-119"><xref:System.ServiceProcess.ServiceProcessInstaller>: describe las características de la clase <xref:System.ServiceProcess.ServiceProcessInstaller>, que se utiliza junto con la clase <xref:System.ServiceProcess.ServiceInstaller> para instalar y desinstalar sus servicios.</span><span class="sxs-lookup"><span data-stu-id="475ec-119"><xref:System.ServiceProcess.ServiceProcessInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>

<span data-ttu-id="475ec-120"><xref:System.ServiceProcess.ServiceInstaller>: describe las características de la clase <xref:System.ServiceProcess.ServiceInstaller>, que se utiliza junto con la clase <xref:System.ServiceProcess.ServiceProcessInstaller> para instalar y desinstalar su servicio.</span><span class="sxs-lookup"><span data-stu-id="475ec-120"><xref:System.ServiceProcess.ServiceInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>

<span data-ttu-id="475ec-121">[Crear proyectos a partir de plantillas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)): describe los tipos de proyectos utilizados en este capítulo y cómo elegir entre ellos.</span><span class="sxs-lookup"><span data-stu-id="475ec-121">[Create Projects from Templates](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) -  Describes the projects types used in this chapter and how to choose between them.</span></span>
