---
title: Funciones externas (F#)
description: Obtenga información sobre la compatibilidad del lenguaje F# para llamar a funciones en código nativo.
ms.date: 05/16/2016
ms.openlocfilehash: db0d3362d867b07b333951f3380c6735ff471d5e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "45973110"
---
# <a name="external-functions"></a><span data-ttu-id="79ecf-103">Funciones externas</span><span class="sxs-lookup"><span data-stu-id="79ecf-103">External Functions</span></span>

<span data-ttu-id="79ecf-104">Este tema describe la compatibilidad del lenguaje F# para llamar a funciones en código nativo.</span><span class="sxs-lookup"><span data-stu-id="79ecf-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="79ecf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79ecf-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="79ecf-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79ecf-106">Remarks</span></span>

<span data-ttu-id="79ecf-107">En la sintaxis anterior, *argumentos* representa los argumentos que se suministran a la `System.Runtime.InteropServices.DllImportAttribute` atributo.</span><span class="sxs-lookup"><span data-stu-id="79ecf-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="79ecf-108">El primer argumento es una cadena que representa el nombre del archivo DLL que contiene esta función, sin la extensión. dll.</span><span class="sxs-lookup"><span data-stu-id="79ecf-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="79ecf-109">Se pueden proporcionar argumentos adicionales para cualquiera de las propiedades públicas de la `System.Runtime.InteropServices.DllImportAttribute` (clase), por ejemplo, la convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="79ecf-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="79ecf-110">Suponga que tiene un archivo DLL de C++ que contiene la siguiente función exportada nativo.</span><span class="sxs-lookup"><span data-stu-id="79ecf-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="79ecf-111">Puede llamar a esta función de F# con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="79ecf-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="79ecf-112">Interoperabilidad con código nativo se conoce como *de invocación de plataforma* y es una característica de CLR.</span><span class="sxs-lookup"><span data-stu-id="79ecf-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="79ecf-113">Para más información, consulte [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="79ecf-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="79ecf-114">La información de esa sección es aplicable a F#.</span><span class="sxs-lookup"><span data-stu-id="79ecf-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="79ecf-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="79ecf-115">See also</span></span>

- [<span data-ttu-id="79ecf-116">Funciones</span><span class="sxs-lookup"><span data-stu-id="79ecf-116">Functions</span></span>](index.md)
