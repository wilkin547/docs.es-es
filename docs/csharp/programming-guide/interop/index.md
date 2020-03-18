---
title: 'Interoperabilidad: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: 3a70d2ae077552bab536e96367cab0fda1661310
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75712057"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="c26f5-102">Interoperabilidad (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c26f5-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="c26f5-103">La interoperabilidad permite conservar y aprovechar las inversiones existentes en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="c26f5-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="c26f5-104">El código que se ejecuta bajo el control de Common Language Runtime (CLR) se denomina *código administrado*, y el código que se ejecuta fuera de CLR se denomina *código no administrado*.</span><span class="sxs-lookup"><span data-stu-id="c26f5-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="c26f5-105">COM, COM+, los componentes de C++, los componentes de ActiveX y la API Windows de Microsoft son ejemplos de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="c26f5-105">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="c26f5-106">.NET Framework habilita la interoperabilidad con código no administrado a través de los servicios de invocación de plataforma, el espacio de nombres <xref:System.Runtime.InteropServices>, la interoperabilidad de C++ y la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="c26f5-106">The .NET Framework enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c26f5-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c26f5-107">In This Section</span></span>  
 [<span data-ttu-id="c26f5-108">Información general sobre interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="c26f5-108">Interoperability Overview</span></span>](./interoperability-overview.md)  
 <span data-ttu-id="c26f5-109">Se describen métodos para habilitar la interoperabilidad entre el código administrado y el código no administrado de C#.</span><span class="sxs-lookup"><span data-stu-id="c26f5-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="c26f5-110">Procedimiento para acceder a objetos de interoperabilidad de Office mediante características de C#</span><span class="sxs-lookup"><span data-stu-id="c26f5-110">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="c26f5-111">Describe las características introducidas en Visual C# para facilitar la programación de Office.</span><span class="sxs-lookup"><span data-stu-id="c26f5-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="c26f5-112">Procedimiento para usar propiedades indizadas en la programación de interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="c26f5-112">How to use indexed properties in COM interop programming</span></span>](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="c26f5-113">Se describe cómo utilizar las propiedades indizadas para acceder a las propiedades de COM que tienen parámetros.</span><span class="sxs-lookup"><span data-stu-id="c26f5-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="c26f5-114">Procedimiento para usar la invocación de plataforma para reproducir un archivo WAV</span><span class="sxs-lookup"><span data-stu-id="c26f5-114">How to use platform invoke to play a WAV file</span></span>](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="c26f5-115">Se describe cómo usar los servicios de invocación de plataforma para reproducir un archivo de sonido .wav en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="c26f5-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="c26f5-116">Tutorial: Programación de Office</span><span class="sxs-lookup"><span data-stu-id="c26f5-116">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)  
 <span data-ttu-id="c26f5-117">Muestra cómo crear un libro de Excel y un documento de Word que contiene un vínculo al libro.</span><span class="sxs-lookup"><span data-stu-id="c26f5-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="c26f5-118">Clase COM de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c26f5-118">Example COM Class</span></span>](./example-com-class.md)  
 <span data-ttu-id="c26f5-119">Muestra cómo exponer una clase de C# como un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="c26f5-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c26f5-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c26f5-120">C# Language Specification</span></span>  

<span data-ttu-id="c26f5-121">Para obtener más información, consulte la sección [Conceptos básicos](~/_csharplang/spec/unsafe-code.md) de [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="c26f5-121">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="c26f5-122">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="c26f5-122">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c26f5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c26f5-123">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c26f5-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c26f5-124">C# Programming Guide</span></span>](../index.md)
- <span data-ttu-id="c26f5-125">[Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="c26f5-125">[Interoperating with Unmanaged Code](../../../framework/interop/index.md)</span></span>
- [<span data-ttu-id="c26f5-126">Tutorial: Programación de Office</span><span class="sxs-lookup"><span data-stu-id="c26f5-126">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
