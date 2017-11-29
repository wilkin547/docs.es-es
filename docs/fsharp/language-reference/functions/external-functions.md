---
title: Funciones externas (F#)
description: "Obtenga información sobre la compatibilidad de idioma de F # para llamar a funciones en código nativo."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 4f525b2b750c2ce42230c61aa0e72f957739b206
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="external-functions"></a><span data-ttu-id="82a1e-104">Funciones externas</span><span class="sxs-lookup"><span data-stu-id="82a1e-104">External Functions</span></span>

<span data-ttu-id="82a1e-105">Este tema describe la compatibilidad de idioma de F # para llamar a funciones en código nativo.</span><span class="sxs-lookup"><span data-stu-id="82a1e-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="82a1e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82a1e-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="82a1e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82a1e-107">Remarks</span></span>

<span data-ttu-id="82a1e-108">En la sintaxis anterior, *argumentos* representa los argumentos que se proporcionan para el `System.Runtime.InteropServices.DllImportAttribute` atributo.</span><span class="sxs-lookup"><span data-stu-id="82a1e-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="82a1e-109">El primer argumento es una cadena que representa el nombre de la DLL que contiene esta función, sin la extensión. dll.</span><span class="sxs-lookup"><span data-stu-id="82a1e-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="82a1e-110">Se pueden proporcionar argumentos adicionales para cualquiera de las propiedades públicas de la `System.Runtime.InteropServices.DllImportAttribute` (clase), por ejemplo, la convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="82a1e-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="82a1e-111">Suponga que tiene un archivo DLL de C++ que contiene la siguiente función exportada nativo.</span><span class="sxs-lookup"><span data-stu-id="82a1e-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="82a1e-112">Puede llamar a esta función de F # mediante el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="82a1e-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="82a1e-113">Interoperabilidad con código nativo se conoce como *de invocación de plataforma* y es una característica de CLR.</span><span class="sxs-lookup"><span data-stu-id="82a1e-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="82a1e-114">Para más información, consulte [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k.aspx) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="82a1e-114">For more information, see [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k.aspx).</span></span> <span data-ttu-id="82a1e-115">La información de esa sección es aplicable a F #.</span><span class="sxs-lookup"><span data-stu-id="82a1e-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="82a1e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="82a1e-116">See Also</span></span>

[<span data-ttu-id="82a1e-117">Funciones</span><span class="sxs-lookup"><span data-stu-id="82a1e-117">Functions</span></span>](index.md)
