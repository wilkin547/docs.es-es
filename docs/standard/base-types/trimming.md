---
title: Recorte y eliminación de caracteres de cadenas en .NET
description: Descubra cómo recortar los espacios en blanco del principio o del final de una cadena, o cómo quitar cualquier número de espacios o caracteres de una posición especificada de la cadena en .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
ms.openlocfilehash: 630fe6b51d151d1f1384f2e3cde62750c303d883
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446898"
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a>Recorte y eliminación de caracteres de cadenas en .NET
Si va a analizar una frase en las palabras que la forman, el resultado pueden ser palabras con espacios en blanco delante y detrás. En este caso, puede usar uno de los métodos de recorte de la clase **System.String** para quitar espacios u otros caracteres de una posición especificada de la cadena. En la tabla siguiente se describen los métodos de recorte disponibles.  
  
|Nombre del método|Usar|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|Quita del comienzo y del final de una cadena los espacios en blanco o los caracteres especificados en una matriz de caracteres.|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|Quita los caracteres especificados de una matriz de caracteres del final de una cadena.|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|Quita los caracteres especificados de una matriz de caracteres del comienzo de una cadena.|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|Quita un número especificado de caracteres de una posición de índice especificada de una cadena.|  
  
## <a name="trim"></a>Trim

 Los espacios en blanco situados delante y detrás de una cadena se pueden quitar fácilmente con el método <xref:System.String.Trim%2A?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente.  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 También se pueden quitar del principio y el final de una cadena los caracteres especificados en una matriz de caracteres. En el ejemplo siguiente se quitan los caracteres de espacio en blanco, los puntos y asteriscos.  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a>TrimEnd

 El método **String.TrimEnd** quita caracteres del final de una cadena, creando un nuevo objeto de cadena. A este método se le pasa una matriz de caracteres para especificar los caracteres que se van a quitar. El orden de los elementos en la matriz de caracteres no afecta a la operación de recorte. El recorte se detiene cuando se encuentra un carácter no especificado en la matriz.  
  
 En el ejemplo siguiente se quitan las últimas letras de una cadena con el método **TrimEnd**. En este ejemplo, se invierte la posición de los caracteres `'r'` y `'W'` para ilustrar que el orden de los caracteres en la matriz no tiene importancia. Observe que este código quita la última palabra de `MyString` y parte de la primera.  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 Con este código se muestra `He` en la consola.  
  
 En el ejemplo siguiente se quita la última palabra de una cadena con el método **TrimEnd**. En este código hay una coma después de `Hello` y, como la coma no está especificada en la matriz de caracteres que se deben recortar, la operación se detiene en la coma.  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 Con este código se muestra `Hello,` en la consola.  
  
## <a name="trimstart"></a>TrimStart

 El método **String.TrimStart** es parecido al método **String.TrimEnd**, con la diferencia de que crea una nueva cadena quitando caracteres del comienzo de un objeto de cadena existente. Al método **TrimStart** se le pasa una matriz de caracteres para especificar los caracteres que se van a quitar. Lo mismo que en el método **TrimEnd**, el orden de los elementos en la matriz de caracteres no afecta a la operación de recorte. El recorte se detiene cuando se encuentra un carácter no especificado en la matriz.  
  
 En el siguiente ejemplo se quita la primera palabra de una cadena. En este ejemplo, se invierte la posición de los caracteres `'l'` y `'H'` para ilustrar que el orden de los caracteres en la matriz no tiene importancia.  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 Con este código se muestra `World!` en la consola.  
  
## <a name="remove"></a>Quitar

 El método <xref:System.String.Remove%2A?displayProperty=nameWithType> quita un número especificado de caracteres, comenzando en una posición especificada de una cadena existente. Este método utiliza un índice basado en cero.  
  
 En el ejemplo siguiente se quitan diez caracteres de una cadena, comenzando en la posición cinco de un índice de base cero de la cadena.  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
## <a name="replace"></a>Sustituya

 También puede quitar un carácter o una subcadena de una cadena llamando al método <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> y especificando una cadena vacía (<xref:System.String.Empty?displayProperty=nameWithType>) como reemplazo. En el ejemplo siguiente se quitan todas las comas de una cadena.  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a>Vea también

- [Operaciones básicas de cadenas](basic-string-operations.md)
