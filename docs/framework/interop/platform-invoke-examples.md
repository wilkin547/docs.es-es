---
title: Ejemplos de invocación de plataforma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89c2043570b9e2798ef41984b889791ddfe1d526
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71051659"
---
# <a name="platform-invoke-examples"></a><span data-ttu-id="88200-102">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="88200-102">Platform Invoke Examples</span></span>
<span data-ttu-id="88200-103">En los ejemplos siguientes se muestra cómo definir y llamar a la función **MessageBox** en User32.dll, pasando una cadena sencilla como argumento.</span><span class="sxs-lookup"><span data-stu-id="88200-103">The following examples demonstrate how to define and call the **MessageBox** function in User32.dll, passing a simple string as an argument.</span></span> <span data-ttu-id="88200-104">En los ejemplos, el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> se establece en **Automático** para permitir que la plataforma de destino determine el ancho de caracteres y la serialización de cadenas.</span><span class="sxs-lookup"><span data-stu-id="88200-104">In the examples, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field is set to **Auto** to let the target platform determine the character width and string marshaling.</span></span>  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)] 
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)] 
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 <span data-ttu-id="88200-105">Para obtener ejemplos adicionales, vea [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="88200-105">For additional examples, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88200-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="88200-106">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="88200-107">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="88200-107">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="88200-108">Especificar un juego de caracteres</span><span class="sxs-lookup"><span data-stu-id="88200-108">Specifying a Character Set</span></span>](specifying-a-character-set.md)
