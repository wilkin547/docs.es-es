---
title: 'Carga de dependencias: .NET Core'
description: Información general sobre la carga de dependencias administradas y no administradas en .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: f6b5fc1f92171b61dcab162b782ca7212c602d76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73416660"
---
# <a name="dependency-loading-in-net-core"></a><span data-ttu-id="88ddc-103">Carga de dependencias en .NET Core</span><span class="sxs-lookup"><span data-stu-id="88ddc-103">Dependency loading in .NET Core</span></span>

<span data-ttu-id="88ddc-104">Todas las aplicaciones .NET Core tienen dependencias.</span><span class="sxs-lookup"><span data-stu-id="88ddc-104">Every .NET Core application has dependencies.</span></span> <span data-ttu-id="88ddc-105">Incluso la aplicación sencilla `hello world` tiene dependencias en partes de las bibliotecas de clases de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88ddc-105">Even the simple `hello world` app has dependencies on portions of the .NET Core class libraries.</span></span>

<span data-ttu-id="88ddc-106">La descripción de la lógica de carga de ensamblados predeterminados de .NET Core puede ayudar a comprender y depurar incidencias de implementación habituales.</span><span class="sxs-lookup"><span data-stu-id="88ddc-106">Understanding .NET Core default assembly loading logic can help understanding and debugging typical deployment issues.</span></span>

<span data-ttu-id="88ddc-107">En algunas aplicaciones, las dependencias se determinan dinámicamente en runtime.</span><span class="sxs-lookup"><span data-stu-id="88ddc-107">In some applications, dependencies are dynamically determined at runtime.</span></span> <span data-ttu-id="88ddc-108">En estas situaciones, es fundamental entender cómo se cargan los ensamblados administrados y las dependencias no administradas.</span><span class="sxs-lookup"><span data-stu-id="88ddc-108">In these situations, it's critical to understand how managed assemblies and unmanaged dependencies are loaded.</span></span>

## <a name="understanding-assemblyloadcontext"></a><span data-ttu-id="88ddc-109">Descripción de AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="88ddc-109">Understanding AssemblyLoadContext</span></span>

<span data-ttu-id="88ddc-110">La API <xref:System.Runtime.Loader.AssemblyLoadContext> es fundamental para el diseño de carga de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88ddc-110">The <xref:System.Runtime.Loader.AssemblyLoadContext> API is central to the .NET Core loading design.</span></span> <span data-ttu-id="88ddc-111">En el artículo [Descripción de AssemblyLoadContext ](understanding-assemblyloadcontext.md) se proporciona información general conceptual para el diseño.</span><span class="sxs-lookup"><span data-stu-id="88ddc-111">The [Understanding AssemblyLoadContext](understanding-assemblyloadcontext.md) article provides a conceptual overview to the design.</span></span>

## <a name="loading-details"></a><span data-ttu-id="88ddc-112">Carga de detalles</span><span class="sxs-lookup"><span data-stu-id="88ddc-112">Loading details</span></span>

<span data-ttu-id="88ddc-113">Los detalles del algoritmo de carga se describen brevemente en varios artículos:</span><span class="sxs-lookup"><span data-stu-id="88ddc-113">The loading algorithm details are covered briefly in several articles:</span></span>

- [<span data-ttu-id="88ddc-114">Algoritmo de carga de ensamblado administrado</span><span class="sxs-lookup"><span data-stu-id="88ddc-114">Managed assembly loading algorithm</span></span>](loading-managed.md)
- [<span data-ttu-id="88ddc-115">Algoritmo de carga de ensamblado satélite</span><span class="sxs-lookup"><span data-stu-id="88ddc-115">Satellite assembly loading algorithm</span></span>](loading-resources.md)
- [<span data-ttu-id="88ddc-116">Algoritmo de carga de biblioteca no administrada (nativa)</span><span class="sxs-lookup"><span data-stu-id="88ddc-116">Unmanaged (native) library loading algorithm</span></span>](loading-unmanaged.md)
- [<span data-ttu-id="88ddc-117">Sondeo predeterminado</span><span class="sxs-lookup"><span data-stu-id="88ddc-117">Default probing</span></span>](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="88ddc-118">Creación de una aplicación de .NET Core con complementos</span><span class="sxs-lookup"><span data-stu-id="88ddc-118">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="88ddc-119">En el tutorial [Creación de una aplicación .NET Core con complementos](../tutorials/creating-app-with-plugin-support.md) se describe cómo crear un elemento AssemblyLoadContext personalizado.</span><span class="sxs-lookup"><span data-stu-id="88ddc-119">The tutorial [Create a .NET Core application with plugins](../tutorials/creating-app-with-plugin-support.md) describes how to create a custom AssemblyLoadContext.</span></span> <span data-ttu-id="88ddc-120">Usa un elemento <xref:System.Runtime.Loader.AssemblyDependencyResolver> para resolver las dependencias del complemento.</span><span class="sxs-lookup"><span data-stu-id="88ddc-120">It uses an <xref:System.Runtime.Loader.AssemblyDependencyResolver> to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="88ddc-121">El tutorial aísla correctamente las dependencias del complemento de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="88ddc-121">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span>

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="88ddc-122">Uso y depuración de la descargabilidad de ensamblado en .NET Core</span><span class="sxs-lookup"><span data-stu-id="88ddc-122">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="88ddc-123">El artículo [Uso y depuración de la descargabilidad de ensamblado en .NET Core](../../standard/assembly/unloadability.md) es un tutorial paso a paso.</span><span class="sxs-lookup"><span data-stu-id="88ddc-123">The [How to use and debug assembly unloadability in .NET Core](../../standard/assembly/unloadability.md) article is a step-by-step tutorial.</span></span> <span data-ttu-id="88ddc-124">Muestra cómo cargar una aplicación .NET Core, ejecutarla y luego descargarla.</span><span class="sxs-lookup"><span data-stu-id="88ddc-124">It shows how to load a .NET Core application, execute, and then unload it.</span></span> <span data-ttu-id="88ddc-125">En el artículo también se proporcionan sugerencias de depuración.</span><span class="sxs-lookup"><span data-stu-id="88ddc-125">The article also provides debugging tips.</span></span>
