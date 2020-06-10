---
title: 'Carga de dependencias: .NET Core'
description: Información general sobre la carga de dependencias administradas y no administradas en .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: 34deb802183f20cc92449c21eb7e149cc002850f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284227"
---
# <a name="dependency-loading-in-net-core"></a><span data-ttu-id="9f5c1-103">Carga de dependencias en .NET Core</span><span class="sxs-lookup"><span data-stu-id="9f5c1-103">Dependency loading in .NET Core</span></span>

<span data-ttu-id="9f5c1-104">Todas las aplicaciones .NET Core tienen dependencias.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-104">Every .NET Core application has dependencies.</span></span> <span data-ttu-id="9f5c1-105">Incluso la aplicación sencilla `hello world` tiene dependencias en partes de las bibliotecas de clases de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-105">Even the simple `hello world` app has dependencies on portions of the .NET Core class libraries.</span></span>

<span data-ttu-id="9f5c1-106">La descripción de la lógica de carga de ensamblados predeterminados de .NET Core puede ayudar a comprender y depurar incidencias de implementación habituales.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-106">Understanding .NET Core default assembly loading logic can help understanding and debugging typical deployment issues.</span></span>

<span data-ttu-id="9f5c1-107">En algunas aplicaciones, las dependencias se determinan dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-107">In some applications, dependencies are dynamically determined at run time.</span></span> <span data-ttu-id="9f5c1-108">En estas situaciones, es fundamental entender cómo se cargan los ensamblados administrados y las dependencias no administradas.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-108">In these situations, it's critical to understand how managed assemblies and unmanaged dependencies are loaded.</span></span>

## <a name="understanding-assemblyloadcontext"></a><span data-ttu-id="9f5c1-109">Descripción de AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="9f5c1-109">Understanding AssemblyLoadContext</span></span>

<span data-ttu-id="9f5c1-110">La API <xref:System.Runtime.Loader.AssemblyLoadContext> es fundamental para el diseño de carga de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-110">The <xref:System.Runtime.Loader.AssemblyLoadContext> API is central to the .NET Core loading design.</span></span> <span data-ttu-id="9f5c1-111">En el artículo [Descripción de AssemblyLoadContext ](understanding-assemblyloadcontext.md) se proporciona información general conceptual para el diseño.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-111">The [Understanding AssemblyLoadContext](understanding-assemblyloadcontext.md) article provides a conceptual overview to the design.</span></span>

## <a name="loading-details"></a><span data-ttu-id="9f5c1-112">Carga de detalles</span><span class="sxs-lookup"><span data-stu-id="9f5c1-112">Loading details</span></span>

<span data-ttu-id="9f5c1-113">Los detalles del algoritmo de carga se describen brevemente en varios artículos:</span><span class="sxs-lookup"><span data-stu-id="9f5c1-113">The loading algorithm details are covered briefly in several articles:</span></span>

- [<span data-ttu-id="9f5c1-114">Algoritmo de carga de ensamblado administrado</span><span class="sxs-lookup"><span data-stu-id="9f5c1-114">Managed assembly loading algorithm</span></span>](loading-managed.md)
- [<span data-ttu-id="9f5c1-115">Algoritmo de carga de ensamblado satélite</span><span class="sxs-lookup"><span data-stu-id="9f5c1-115">Satellite assembly loading algorithm</span></span>](loading-resources.md)
- [<span data-ttu-id="9f5c1-116">Algoritmo de carga de biblioteca no administrada (nativa)</span><span class="sxs-lookup"><span data-stu-id="9f5c1-116">Unmanaged (native) library loading algorithm</span></span>](loading-unmanaged.md)
- [<span data-ttu-id="9f5c1-117">Sondeo predeterminado</span><span class="sxs-lookup"><span data-stu-id="9f5c1-117">Default probing</span></span>](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="9f5c1-118">Creación de una aplicación de .NET Core con complementos</span><span class="sxs-lookup"><span data-stu-id="9f5c1-118">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="9f5c1-119">En el tutorial [Creación de una aplicación .NET Core con complementos](../tutorials/creating-app-with-plugin-support.md) se describe cómo crear un elemento AssemblyLoadContext personalizado.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-119">The tutorial [Create a .NET Core application with plugins](../tutorials/creating-app-with-plugin-support.md) describes how to create a custom AssemblyLoadContext.</span></span> <span data-ttu-id="9f5c1-120">Usa un elemento <xref:System.Runtime.Loader.AssemblyDependencyResolver> para resolver las dependencias del complemento.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-120">It uses an <xref:System.Runtime.Loader.AssemblyDependencyResolver> to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="9f5c1-121">El tutorial aísla correctamente las dependencias del complemento de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-121">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span>

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="9f5c1-122">Uso y depuración de la descargabilidad de ensamblado en .NET Core</span><span class="sxs-lookup"><span data-stu-id="9f5c1-122">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="9f5c1-123">El artículo [Uso y depuración de la descargabilidad de ensamblado en .NET Core](../../standard/assembly/unloadability.md) es un tutorial paso a paso.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-123">The [How to use and debug assembly unloadability in .NET Core](../../standard/assembly/unloadability.md) article is a step-by-step tutorial.</span></span> <span data-ttu-id="9f5c1-124">Muestra cómo cargar una aplicación .NET Core, ejecutarla y luego descargarla.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-124">It shows how to load a .NET Core application, execute, and then unload it.</span></span> <span data-ttu-id="9f5c1-125">En el artículo también se proporcionan sugerencias de depuración.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-125">The article also provides debugging tips.</span></span>
