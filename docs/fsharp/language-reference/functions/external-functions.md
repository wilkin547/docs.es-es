---
title: Funciones externas (F#)
description: 'Obtenga información sobre la compatibilidad de idioma de F # para llamar a funciones en código nativo.'
ms.date: 05/16/2016
ms.openlocfilehash: 398697c5e0deab7f8d81ec5198ab1918bd865e13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564487"
---
# <a name="external-functions"></a><span data-ttu-id="8b225-103">Funciones externas</span><span class="sxs-lookup"><span data-stu-id="8b225-103">External Functions</span></span>

<span data-ttu-id="8b225-104">Este tema describe la compatibilidad de idioma de F # para llamar a funciones en código nativo.</span><span class="sxs-lookup"><span data-stu-id="8b225-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b225-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b225-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="8b225-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8b225-106">Remarks</span></span>

<span data-ttu-id="8b225-107">En la sintaxis anterior, *argumentos* representa los argumentos que se proporcionan para el `System.Runtime.InteropServices.DllImportAttribute` atributo.</span><span class="sxs-lookup"><span data-stu-id="8b225-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="8b225-108">El primer argumento es una cadena que representa el nombre de la DLL que contiene esta función, sin la extensión. dll.</span><span class="sxs-lookup"><span data-stu-id="8b225-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="8b225-109">Se pueden proporcionar argumentos adicionales para cualquiera de las propiedades públicas de la `System.Runtime.InteropServices.DllImportAttribute` (clase), por ejemplo, la convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="8b225-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="8b225-110">Suponga que tiene un archivo DLL de C++ que contiene la siguiente función exportada nativo.</span><span class="sxs-lookup"><span data-stu-id="8b225-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="8b225-111">Puede llamar a esta función de F # mediante el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="8b225-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="8b225-112">Interoperabilidad con código nativo se conoce como *de invocación de plataforma* y es una característica de CLR.</span><span class="sxs-lookup"><span data-stu-id="8b225-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="8b225-113">Para más información, consulte [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="8b225-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="8b225-114">La información de esa sección es aplicable a F #.</span><span class="sxs-lookup"><span data-stu-id="8b225-114">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="8b225-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b225-115">See Also</span></span>

[<span data-ttu-id="8b225-116">Funciones</span><span class="sxs-lookup"><span data-stu-id="8b225-116">Functions</span></span>](index.md)
