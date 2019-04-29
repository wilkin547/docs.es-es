---
title: Funciones externas
description: Obtenga información sobre la F# compatibilidad de lenguaje para llamar a funciones en código nativo.
ms.date: 05/16/2016
ms.openlocfilehash: 86ea78844fb812361233f8360c377465d83be203
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934633"
---
# <a name="external-functions"></a><span data-ttu-id="94f95-103">Funciones externas</span><span class="sxs-lookup"><span data-stu-id="94f95-103">External Functions</span></span>

<span data-ttu-id="94f95-104">Este tema se describe F# compatibilidad de lenguaje para llamar a funciones en código nativo.</span><span class="sxs-lookup"><span data-stu-id="94f95-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="94f95-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94f95-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="94f95-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94f95-106">Remarks</span></span>

<span data-ttu-id="94f95-107">En la sintaxis anterior, *argumentos* representa los argumentos que se suministran a la `System.Runtime.InteropServices.DllImportAttribute` atributo.</span><span class="sxs-lookup"><span data-stu-id="94f95-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="94f95-108">El primer argumento es una cadena que representa el nombre del archivo DLL que contiene esta función, sin la extensión. dll.</span><span class="sxs-lookup"><span data-stu-id="94f95-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="94f95-109">Se pueden proporcionar argumentos adicionales para cualquiera de las propiedades públicas de la `System.Runtime.InteropServices.DllImportAttribute` (clase), por ejemplo, la convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="94f95-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="94f95-110">Suponga que tiene un archivo DLL de C++ que contiene la siguiente función exportada nativo.</span><span class="sxs-lookup"><span data-stu-id="94f95-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="94f95-111">Puede llamar a esta función desde F# con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="94f95-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="94f95-112">Interoperabilidad con código nativo se conoce como *de invocación de plataforma* y es una característica de CLR.</span><span class="sxs-lookup"><span data-stu-id="94f95-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="94f95-113">Para más información, consulte [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="94f95-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="94f95-114">La información de esa sección es aplicable a F#.</span><span class="sxs-lookup"><span data-stu-id="94f95-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="94f95-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="94f95-115">See also</span></span>

- [<span data-ttu-id="94f95-116">Funciones</span><span class="sxs-lookup"><span data-stu-id="94f95-116">Functions</span></span>](index.md)