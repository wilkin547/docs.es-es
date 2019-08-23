---
title: Funciones externas
description: Obtenga información sobre F# la compatibilidad de lenguajes para llamar a funciones en código nativo.
ms.date: 05/16/2016
ms.openlocfilehash: 3c8edaba25e07b6ca2c44a58c4b55dc98a13b4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968726"
---
# <a name="external-functions"></a><span data-ttu-id="5607b-103">Funciones externas</span><span class="sxs-lookup"><span data-stu-id="5607b-103">External Functions</span></span>

<span data-ttu-id="5607b-104">En este tema F# se describe la compatibilidad con lenguajes para llamar a funciones en código nativo.</span><span class="sxs-lookup"><span data-stu-id="5607b-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="5607b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5607b-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="5607b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5607b-106">Remarks</span></span>

<span data-ttu-id="5607b-107">En la sintaxis anterior, *arguments* representa los `System.Runtime.InteropServices.DllImportAttribute` argumentos que se proporcionan al atributo.</span><span class="sxs-lookup"><span data-stu-id="5607b-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="5607b-108">El primer argumento es una cadena que representa el nombre del archivo DLL que contiene esta función, sin la extensión. dll.</span><span class="sxs-lookup"><span data-stu-id="5607b-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="5607b-109">Se pueden proporcionar argumentos adicionales para cualquiera de las propiedades públicas de la `System.Runtime.InteropServices.DllImportAttribute` clase, como la Convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="5607b-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="5607b-110">Suponga que tiene un archivo C++ dll nativo que contiene la siguiente función exportada.</span><span class="sxs-lookup"><span data-stu-id="5607b-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="5607b-111">Puede llamar a esta función desde F# mediante el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5607b-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="5607b-112">La interoperabilidad con código nativo se conoce como invocación de *plataforma* y es una característica de CLR.</span><span class="sxs-lookup"><span data-stu-id="5607b-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="5607b-113">Para más información, consulte [Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="5607b-113">For more information, see [Interoperating with Unmanaged Code](../../../framework/interop/index.md).</span></span> <span data-ttu-id="5607b-114">La información de esa sección es aplicable a F#.</span><span class="sxs-lookup"><span data-stu-id="5607b-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="5607b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5607b-115">See also</span></span>

- [<span data-ttu-id="5607b-116">Funciones</span><span class="sxs-lookup"><span data-stu-id="5607b-116">Functions</span></span>](index.md)
