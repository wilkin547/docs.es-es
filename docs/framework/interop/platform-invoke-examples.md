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
ms.openlocfilehash: 358d1ce662d56b8c31124f4b3264ec25a0f94586
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181329"
---
# <a name="platform-invoke-examples"></a><span data-ttu-id="ffb7b-102">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="ffb7b-102">Platform Invoke Examples</span></span>
<span data-ttu-id="ffb7b-103">En los ejemplos siguientes se muestra cómo definir y llamar a la función **MessageBox** en User32.dll, pasando una cadena sencilla como argumento.</span><span class="sxs-lookup"><span data-stu-id="ffb7b-103">The following examples demonstrate how to define and call the **MessageBox** function in User32.dll, passing a simple string as an argument.</span></span> <span data-ttu-id="ffb7b-104">En los ejemplos, el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> se establece en **Automático** para permitir que la plataforma de destino determine el ancho de caracteres y la serialización de cadenas.</span><span class="sxs-lookup"><span data-stu-id="ffb7b-104">In the examples, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field is set to **Auto** to let the target platform determine the character width and string marshaling.</span></span>  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)]
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)]
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 <span data-ttu-id="ffb7b-105">Para obtener ejemplos adicionales, vea [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="ffb7b-105">For additional examples, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffb7b-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ffb7b-106">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="ffb7b-107">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="ffb7b-107">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="ffb7b-108">Especificar un juego de caracteres</span><span class="sxs-lookup"><span data-stu-id="ffb7b-108">Specifying a Character Set</span></span>](specifying-a-character-set.md)
