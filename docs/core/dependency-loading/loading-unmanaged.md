---
title: 'Algoritmo de carga de biblioteca no administrada: .NET Core'
description: Descripción de los detalles del algoritmo de carga de ensamblado no administrado en .NET Core
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72303699"
---
# <a name="unmanaged-native-library-loading-algorithm"></a><span data-ttu-id="b94be-103">Algoritmo de carga de biblioteca no administrada (nativa)</span><span class="sxs-lookup"><span data-stu-id="b94be-103">Unmanaged (native) library loading algorithm</span></span>

<span data-ttu-id="b94be-104">Las bibliotecas no administradas se ubican y se cargan con un algoritmo que implica varias fases.</span><span class="sxs-lookup"><span data-stu-id="b94be-104">Unmanaged libraries are located and loaded with an algorithm involving various stages.</span></span>

<span data-ttu-id="b94be-105">El algoritmo siguiente describe cómo se cargan las bibliotecas nativas a través de `PInvoke`.</span><span class="sxs-lookup"><span data-stu-id="b94be-105">The following algorithm describes how native libraries are loaded through `PInvoke`.</span></span>

## <a name="pinvoke-load-library-algorithm"></a><span data-ttu-id="b94be-106">Algoritmo de la biblioteca de carga `PInvoke`</span><span class="sxs-lookup"><span data-stu-id="b94be-106">`PInvoke` load library algorithm</span></span>

<span data-ttu-id="b94be-107">`PInvoke` usa el algoritmo siguiente al intentar cargar un ensamblado no administrado:</span><span class="sxs-lookup"><span data-stu-id="b94be-107">`PInvoke` uses the following algorithm when attempting to load an unmanaged assembly:</span></span>

1. <span data-ttu-id="b94be-108">Determine el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> `active`.</span><span class="sxs-lookup"><span data-stu-id="b94be-108">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="b94be-109">En el caso de una biblioteca de carga no administrada, el elemento AssemblyLoadContext de `active` es el que tiene el ensamblado que define `PInvoke`.</span><span class="sxs-lookup"><span data-stu-id="b94be-109">For an unmanaged load library, the `active` AssemblyLoadContext is the one with the assembly that defines the `PInvoke`.</span></span>

2. <span data-ttu-id="b94be-110">En el caso del elemento <xref:System.Runtime.Loader.AssemblyLoadContext> `active`, intente buscar el ensamblado en orden de prioridad por:</span><span class="sxs-lookup"><span data-stu-id="b94be-110">For the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, try to find the assembly in priority order by:</span></span>
    * <span data-ttu-id="b94be-111">Comprobar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b94be-111">Checking its cache.</span></span>

    * <span data-ttu-id="b94be-112">Llamar al delegado <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> actual que establece la función <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b94be-112">Calling the current <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegate set by the <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> function.</span></span>

    * <span data-ttu-id="b94be-113">Llamar a la función <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> en el elemento AssemblyLoadContext de `active`.</span><span class="sxs-lookup"><span data-stu-id="b94be-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> function on the `active` AssemblyLoadContext.</span></span>

    * <span data-ttu-id="b94be-114">Comprobar la memoria caché de la instancia de <xref:System.AppDomain> y ejecutar la lógica de [sondeo de biblioteca no administrada (nativa)](default-probing.md#unmanaged-native-library-probing).</span><span class="sxs-lookup"><span data-stu-id="b94be-114">Checking the <xref:System.AppDomain> instance's cache and running the [Unmanaged (native) library probing](default-probing.md#unmanaged-native-library-probing) logic.</span></span>

    * <span data-ttu-id="b94be-115">Generar el evento <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> para el elemento AssemblyLoadContext de `active`.</span><span class="sxs-lookup"><span data-stu-id="b94be-115">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> event for the `active` AssemblyLoadContext.</span></span>
