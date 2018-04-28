---
title: Funciones externas (F#)
description: 'Obtenga información sobre la compatibilidad de idioma de F # para llamar a funciones en código nativo.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 28e74258d91ff2d9742caa7a6c06f515cd987c0a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="external-functions"></a><span data-ttu-id="e5936-103">Funciones externas</span><span class="sxs-lookup"><span data-stu-id="e5936-103">External Functions</span></span>

<span data-ttu-id="e5936-104">Este tema describe la compatibilidad de idioma de F # para llamar a funciones en código nativo.</span><span class="sxs-lookup"><span data-stu-id="e5936-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="e5936-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5936-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="e5936-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5936-106">Remarks</span></span>

<span data-ttu-id="e5936-107">En la sintaxis anterior, *argumentos* representa los argumentos que se proporcionan para el `System.Runtime.InteropServices.DllImportAttribute` atributo.</span><span class="sxs-lookup"><span data-stu-id="e5936-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="e5936-108">El primer argumento es una cadena que representa el nombre de la DLL que contiene esta función, sin la extensión. dll.</span><span class="sxs-lookup"><span data-stu-id="e5936-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="e5936-109">Se pueden proporcionar argumentos adicionales para cualquiera de las propiedades públicas de la `System.Runtime.InteropServices.DllImportAttribute` (clase), por ejemplo, la convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="e5936-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="e5936-110">Suponga que tiene un archivo DLL de C++ que contiene la siguiente función exportada nativo.</span><span class="sxs-lookup"><span data-stu-id="e5936-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="e5936-111">Puede llamar a esta función de F # mediante el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="e5936-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="e5936-112">Interoperabilidad con código nativo se conoce como *de invocación de plataforma* y es una característica de CLR.</span><span class="sxs-lookup"><span data-stu-id="e5936-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="e5936-113">Para más información, consulte [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="e5936-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="e5936-114">La información de esa sección es aplicable a F #.</span><span class="sxs-lookup"><span data-stu-id="e5936-114">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="e5936-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5936-115">See Also</span></span>

[<span data-ttu-id="e5936-116">Funciones</span><span class="sxs-lookup"><span data-stu-id="e5936-116">Functions</span></span>](index.md)
