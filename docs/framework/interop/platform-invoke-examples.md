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
ms.openlocfilehash: da157a40819ada3914cf1791c8ca3f7b30e8c837
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124758"
---
# <a name="platform-invoke-examples"></a>Ejemplos de invocación de plataforma
En los ejemplos siguientes se muestra cómo definir y llamar a la función **MessageBox** en User32.dll, pasando una cadena sencilla como argumento. En los ejemplos, el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> se establece en **Automático** para permitir que la plataforma de destino determine el ancho de caracteres y la serialización de cadenas.  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)] 
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)] 
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 Para obtener ejemplos adicionales, vea [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Crear prototipos en código administrado](creating-prototypes-in-managed-code.md)
- [Especificar un juego de caracteres](specifying-a-character-set.md)
