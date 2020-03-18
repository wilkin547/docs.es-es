---
title: Documentación de .NET Framework
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
ms.openlocfilehash: d94d97cd1b519025ff360dc903558ea3656818d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181532"
---
# <a name="net-framework-guide"></a><span data-ttu-id="148ba-102">Guía de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="148ba-102">.NET Framework guide</span></span>

> [!NOTE]
> <span data-ttu-id="148ba-103">Este conjunto de contenido de .NET Framework incluye información de las versiones 4.5 y 4.8 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="148ba-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="148ba-104">Para descargar .NET Framework, consulte [Instalación de .NET Framework](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="148ba-104">To download .NET Framework, see [Install .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="148ba-105">Para obtener una lista de nuevas características y cambios en .NET Framework, consulte [Novedades de .NET Framework](./whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="148ba-105">For a list of new features and changes in .NET Framework, see [What's New in .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="148ba-106">Para una lista de las plataformas compatibles, consulte los [requisitos del sistema de .NET Framework](./get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="148ba-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="148ba-107">Para ver documentación sobre las versiones anteriores de .NET Framework, consulte la [documentación de versiones anteriores de .NET](https://docs.microsoft.com/previous-versions/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="148ba-107">For documentation about older versions of .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="148ba-108">.NET Framework es una plataforma de desarrollo para compilar aplicaciones para la Web, Windows, Windows Phone, Windows Server y Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="148ba-108">.NET Framework is a development platform for building apps for web, Windows, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="148ba-109">Consta del Common Language Runtime (CLR) y la biblioteca de clases .NET Framework, que incluye una amplia gama de características y compatibilidad con muchos estándares del sector.</span><span class="sxs-lookup"><span data-stu-id="148ba-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="148ba-110">.NET Framework proporciona muchos servicios, como la administración de memoria, la seguridad de tipos y memoria, opciones de seguridad, redes y la implementación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="148ba-110">.NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="148ba-111">Proporciona API y estructuras de datos fáciles de usar que abstraen el sistema operativo de Windows de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="148ba-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="148ba-112">Con .NET Framework se pueden usar diferentes lenguajes de programación, incluidos C#, F# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="148ba-112">You can use different programming languages with .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="148ba-113">Para obtener una introducción general a .NET Framework para usuarios y desarrolladores, vea [Introducción](./get-started/index.md).</span><span class="sxs-lookup"><span data-stu-id="148ba-113">For a general introduction to .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="148ba-114">Para obtener una introducción a la arquitectura y las características principales de .NET Framework, consulte la [información general](./get-started/overview.md).</span><span class="sxs-lookup"><span data-stu-id="148ba-114">For an introduction to the architecture and key features of .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="148ba-115">.NET Framework se puede usar con Docker y con [contenedores de Windows](/virtualization/windowscontainers/about/).</span><span class="sxs-lookup"><span data-stu-id="148ba-115">.NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="148ba-116">Instalación</span><span class="sxs-lookup"><span data-stu-id="148ba-116">Installation</span></span>

<span data-ttu-id="148ba-117">.NET Framework se integra con Windows, lo que permite ejecutar aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="148ba-117">.NET Framework comes with Windows, which enables you to run .NET Framework applications.</span></span> <span data-ttu-id="148ba-118">Es posible que necesite una versión de .NET Framework posterior a la que se incluye con su versión de Windows.</span><span class="sxs-lookup"><span data-stu-id="148ba-118">You may need a later version of .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="148ba-119">Para obtener más información, consulte [Instalación de .NET Framework en Windows](./install/index.md).</span><span class="sxs-lookup"><span data-stu-id="148ba-119">For more information, see [Install .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="148ba-120">Para saber cómo reparar la instalación de .NET Framework si se producen errores al instalarlo, vea [Reparación de .NET Framework](./install/repair.md).</span><span class="sxs-lookup"><span data-stu-id="148ba-120">To learn how to repair your .NET Framework installation if you're experiencing errors during installation, see [Repair .NET Framework](./install/repair.md).</span></span>

<span data-ttu-id="148ba-121">Para obtener información detallada sobre cómo descargar .NET Framework, vea [Instalación de .NET Framework para desarrolladores](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="148ba-121">For more detailed information on downloading .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="148ba-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="148ba-122">In this section</span></span>

* [<span data-ttu-id="148ba-123">Novedades</span><span class="sxs-lookup"><span data-stu-id="148ba-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="148ba-124">Describe las nuevas características clave y los cambios realizados en las versiones más recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="148ba-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="148ba-125">Incluye listas de los tipos y miembros obsoletos y proporciona una guía para migrar las aplicaciones desde la versión anterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="148ba-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="148ba-126">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="148ba-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="148ba-127">Proporciona información general completa de .NET Framework y vínculos a recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="148ba-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="148ba-128">Guía de instalación</span><span class="sxs-lookup"><span data-stu-id="148ba-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="148ba-129">Proporciona recursos y orientación sobre la instalación y la solución de problemas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="148ba-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="148ba-130">Guía de migración</span><span class="sxs-lookup"><span data-stu-id="148ba-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="148ba-131">Proporciona recursos y una lista de cambios que debe tener en cuenta si migra la aplicación a una nueva versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="148ba-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="148ba-132">Guía de desarrollo</span><span class="sxs-lookup"><span data-stu-id="148ba-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="148ba-133">Proporciona una guía para todas las áreas y tareas tecnológicas principales para el desarrollo de aplicaciones, como la creación, configuración, depuración, seguridad e implementación de la aplicación, e información sobre programación dinámica, interoperabilidad, extensibilidad, administración de memoria y subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="148ba-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="148ba-134">Herramientas</span><span class="sxs-lookup"><span data-stu-id="148ba-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="148ba-135">Describe las herramientas que ayudan a desarrollar, configurar e implementar aplicaciones con las tecnologías de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="148ba-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="148ba-136">Bibliotecas de clases y API adicionales</span><span class="sxs-lookup"><span data-stu-id="148ba-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="148ba-137">Proporciona documentación de las API de .NET Framework privadas que usan las herramientas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="148ba-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="148ba-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="148ba-138">See also</span></span>

* [<span data-ttu-id="148ba-139">Biblioteca de clases .NET Framework</span><span class="sxs-lookup"><span data-stu-id="148ba-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
