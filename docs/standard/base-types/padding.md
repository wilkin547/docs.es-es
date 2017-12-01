---
title: Cadenas de relleno en .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29cd40645cf06ac9babb4738259938a3da04a155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="padding-strings-in-net"></a>Cadenas de relleno en .NET
Utilice uno de los siguientes <xref:System.String> métodos para crear una nueva cadena que consta de una cadena original que se rellena con iniciales o finales de caracteres con la longitud total especificada. El carácter de relleno puede ser un espacio o un carácter especificado y, por tanto, parece que está alineado a la derecha o a la izquierda.  
  
|Nombre del método|Uso|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|Rellena una cadena con caracteres iniciales hasta una longitud total especificada.|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|Rellena una cadena con caracteres finales hasta una longitud total especificada.|  
  
## <a name="padleft"></a>PadLeft  
 El <xref:System.String.PadLeft%2A?displayProperty=nameWithType> método crea una nueva cadena concatenando caracteres de relleno iniciales a una cadena original hasta alcanzar la longitud total especificada. El <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> método usa el espacio en blanco como el carácter de relleno y el <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> método le permite especificar su propio carácter de relleno.  
  
 El siguiente ejemplo de código utiliza el <xref:System.String.PadLeft%2A> método para crear una nueva cadena que tiene veinte caracteres. En el ejemplo se muestra "`--------Hello World!`" en la consola.  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a>PadRight  
 El <xref:System.String.PadRight%2A?displayProperty=nameWithType> método crea una nueva cadena concatenando caracteres de relleno finales a una cadena original hasta alcanzar la longitud total especificada. El <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> método usa el espacio en blanco como el carácter de relleno y el <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> método le permite especificar su propio carácter de relleno.  
  
 El siguiente ejemplo de código utiliza el <xref:System.String.PadRight%2A> método para crear una nueva cadena que tiene veinte caracteres. En el ejemplo se muestra "`Hello World!--------`" en la consola.  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a>Vea también  
 [Operaciones básicas de cadenas](../../../docs/standard/base-types/basic-string-operations.md)
