---
title: Comparación de cadenas en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- value comparisons of strings
- LastIndexOf method
- CompareTo method
- IndexOf method
- Compare method
- strings [.NET Framework], comparing
- CompareOrdinal method
- EndsWith method
- Equals method
- StartsWith method
ms.assetid: 977dc094-fe19-4955-98ec-d2294d04a4ba
ms.openlocfilehash: 7997f3098265b76f8fe2ef4fc7ab0e17f6e81d69
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289335"
---
# <a name="comparing-strings-in-net"></a>Comparación de cadenas en .NET
.NET proporciona varios métodos para comparar los valores de cadenas. En la tabla siguiente se enumeran y describen los métodos de comparación de valores.  
  
|Nombre del método|Usar|  
|-----------------|---------|  
|<xref:System.String.Compare%2A?displayProperty=nameWithType>|Compara los valores de dos cadenas. Devuelve un valor entero.|  
|<xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType>|Compara dos cadenas independientemente de la referencia cultural local. Devuelve un valor entero.|  
|<xref:System.String.CompareTo%2A?displayProperty=nameWithType>|Compara el objeto de cadena actual con otra cadena. Devuelve un valor entero.|  
|<xref:System.String.StartsWith%2A?displayProperty=nameWithType>|Determina si una cadena comienza con la cadena que se pasa. Devuelve un valor booleano.|  
|<xref:System.String.EndsWith%2A?displayProperty=nameWithType>|Determina si una cadena termina con la cadena que se pasa. Devuelve un valor booleano.|  
|<xref:System.String.Equals%2A?displayProperty=nameWithType>|Determina si dos cadenas son iguales. Devuelve un valor booleano.|  
|<xref:System.String.IndexOf%2A?displayProperty=nameWithType>|Devuelve la posición de índice de un carácter o cadena, empezando en el comienzo de la cadena que se examina. Devuelve un valor entero.|  
|<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>|Devuelve la posición de índice de un carácter o cadena, empezando en el final de la cadena que se examina. Devuelve un valor entero.|  
  
## <a name="compare"></a>Comparar  
 El método <xref:System.String.Compare%2A?displayProperty=nameWithType> estático proporciona una manera de comparar dos cadenas exhaustivamente. En este método se tiene en cuenta la referencia cultural. Esta función se puede usar para comparar dos cadenas o subcadenas de dos cadenas. Además, se proporcionan sobrecargas para tener en cuenta o no las diferencias de referencia cultural y de mayúsculas y minúsculas. En la tabla siguiente, se muestran los tres valores enteros que este método puede devolver.  
  
|Valor devuelto|Condición|  
|------------------|---------------|  
|Un entero negativo|La primera cadena precede a la segunda cadena en el criterio de ordenación.<br /><br /> o bien<br /><br /> La primera cadena es `null`.|  
|0|La primera y la segunda cadena son iguales.<br /><br /> o bien<br /><br /> Ambas cadenas son `null`.|  
|Un entero positivo.<br /><br /> o bien<br /><br /> 1|La primera cadena sigue a la segunda cadena en el criterio de ordenación.<br /><br /> o bien<br /><br /> La segunda cadena es `null`.|  
  
> [!IMPORTANT]
> La finalidad principal del método <xref:System.String.Compare%2A?displayProperty=nameWithType> es que se utilice para la ordenación o clasificación de cadenas. El método <xref:System.String.Compare%2A?displayProperty=nameWithType> no debe utilizarse para comprobar la igualdad (es decir, para buscar explícitamente un valor devuelto que sea 0 sin tener en cuenta si una cadena es menor o mayor que otra). En su lugar, para determinar si dos cadenas son iguales, use el método <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .  
  
 En el ejemplo siguiente, se usa el método <xref:System.String.Compare%2A?displayProperty=nameWithType> para determinar los valores relativos de dos cadenas.  
  
 [!code-cpp[Conceptual.String.BasicOps#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#6)]
 [!code-csharp[Conceptual.String.BasicOps#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#6)]
 [!code-vb[Conceptual.String.BasicOps#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#6)]  
  
 Con este ejemplo se muestra `-1` en la consola.  
  
 En el ejemplo anterior se tienen en cuenta las referencias culturales de forma predeterminada. Para realizar una comparación de cadenas que no tenga en cuenta las referencias culturales, utilice una sobrecarga del método <xref:System.String.Compare%2A?displayProperty=nameWithType> ya que permite especificar la referencia cultural que se debe utilizar mediante un parámetro de *referencia cultural* . Para obtener un ejemplo que muestra cómo utilizar el método <xref:System.String.Compare%2A?displayProperty=nameWithType> para realizar una comparación de este tipo, consulte [Realizar comparaciones de cadenas que no tienen en cuenta las referencias culturales](../globalization-localization/performing-culture-insensitive-string-comparisons.md).  
  
## <a name="compareordinal"></a>CompareOrdinal  
 El método <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> compara dos objetos de cadena sin tener en cuenta la referencia cultural local. Los valores devueltos de este método son idénticos a los que devolvía el método **Compare** en la tabla anterior.  
  
> [!IMPORTANT]
> La finalidad principal del método <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> es que se utilice para la ordenación o clasificación de cadenas. El método <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> no debe utilizarse para comprobar la igualdad (es decir, para buscar explícitamente un valor devuelto que sea 0 sin tener en cuenta si una cadena es menor o mayor que otra). En su lugar, para determinar si dos cadenas son iguales, use el método <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .  
  
 En el ejemplo siguiente se usa el método **CompareOrdinal** para comparar los valores de dos cadenas.  
  
 [!code-cpp[Conceptual.String.BasicOps#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#7)]
 [!code-csharp[Conceptual.String.BasicOps#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#7)]
 [!code-vb[Conceptual.String.BasicOps#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#7)]  
  
 Con este ejemplo se muestra `-32` en la consola.  
  
## <a name="compareto"></a>CompareTo  
 El método <xref:System.String.CompareTo%2A?displayProperty=nameWithType> compara la cadena que encapsula el objeto de cadena actual con otra cadena u objeto. Los valores devueltos de este método son idénticos a los que devolvía el método <xref:System.String.Compare%2A?displayProperty=nameWithType> en la tabla anterior.  
  
> [!IMPORTANT]
> La finalidad principal del método <xref:System.String.CompareTo%2A?displayProperty=nameWithType> es que se utilice para la ordenación o clasificación de cadenas. El método <xref:System.String.CompareTo%2A?displayProperty=nameWithType> no debe utilizarse para comprobar la igualdad (es decir, para buscar explícitamente un valor devuelto que sea 0 sin tener en cuenta si una cadena es menor o mayor que otra). En su lugar, para determinar si dos cadenas son iguales, use el método <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .  
  
 En el ejemplo siguiente se usa el método <xref:System.String.CompareTo%2A?displayProperty=nameWithType> para comparar los objetos `string1` y `string2` .  
  
 [!code-cpp[Conceptual.String.BasicOps#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#8)]
 [!code-csharp[Conceptual.String.BasicOps#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#8)]
 [!code-vb[Conceptual.String.BasicOps#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#8)]  
  
 Con este ejemplo se muestra `-1` en la consola.  
  
 Todas las sobrecargas del método <xref:System.String.CompareTo%2A?displayProperty=nameWithType> realizan comparaciones que tienen en cuenta las referencias culturales y las mayúsculas y minúsculas de manera predeterminada. No se proporcionan sobrecargas de este método que permitan realizar una comparación que no tenga en cuenta las referencias culturales Para lograr claridad en el código, se recomienda utilizar el método **String.Compare** en su lugar, especificando <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> para las operaciones que tienen en cuenta la referencia cultural o <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> para las operaciones que no la tienen en cuenta. Para obtener ejemplos que muestran cómo utilizar el método **String.Compare** para realizar comparaciones de este tipo, vea [Realizar comparaciones de cadenas que no tienen en cuenta las referencias culturales](../globalization-localization/performing-culture-insensitive-string-comparisons.md).  
  
## <a name="equals"></a>Es igual a  
 El método **String.Equals** puede determinar con facilidad si dos cadenas son iguales. Este método distingue entre mayúsculas y minúsculas y devuelve un valor booleano **True** o **False** . Se puede usar desde una clase existente, como se muestra en el siguiente ejemplo. En el ejemplo siguiente se usa el método **Equals** para determinar si un objeto de cadena contiene la frase "Hello World".  
  
 [!code-cpp[Conceptual.String.BasicOps#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#9)]
 [!code-csharp[Conceptual.String.BasicOps#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#9)]
 [!code-vb[Conceptual.String.BasicOps#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#9)]  
  
 Con este ejemplo se muestra `True` en la consola.  
  
 Este método se puede usar también como método estático. En el ejemplo siguiente se comparan dos objetos de cadena utilizando un método estático.  
  
 [!code-cpp[Conceptual.String.BasicOps#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#10)]
 [!code-csharp[Conceptual.String.BasicOps#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#10)]
 [!code-vb[Conceptual.String.BasicOps#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#10)]  
  
 Con este ejemplo se muestra `True` en la consola.  
  
## <a name="startswith-and-endswith"></a>StartsWith y EndsWith  
 El método **String.StartsWith** se puede usar para determinar si un objeto de cadena comienza con los mismos caracteres que forman otra cadena. Este método distingue entre mayúsculas y minúsculas y devuelve **true** si el objeto de cadena actual comienza con la cadena que se pasa y **false** si no lo hace. En el ejemplo siguiente se usa este método para determinar si un objeto de cadena comienza con "Hello".  
  
 [!code-cpp[Conceptual.String.BasicOps#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#11)]
 [!code-csharp[Conceptual.String.BasicOps#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#11)]
 [!code-vb[Conceptual.String.BasicOps#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#11)]  
  
 Con este ejemplo se muestra `True` en la consola.  
  
 El método **String.EndsWith** compara la cadena que se pasa con los caracteres del final del objeto de cadena actual. También devuelve un valor booleano. En el ejemplo siguiente se comprueba el final de una cadena con el método **EndsWith** .  
  
 [!code-cpp[Conceptual.String.BasicOps#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#12)]
 [!code-csharp[Conceptual.String.BasicOps#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#12)]
 [!code-vb[Conceptual.String.BasicOps#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#12)]  
  
 Con este ejemplo se muestra `False` en la consola.  
  
## <a name="indexof-and-lastindexof"></a>IndexOf y LastIndexOf  
 El método **String.IndexOf** se puede usar para determinar la posición de la primera aparición de un carácter concreto dentro de una cadena. Este método, que distingue entre mayúsculas y minúsculas, empieza a contar desde el comienzo de una cadena y devuelve la posición del carácter que se pasa utilizando un índice de base cero. Si no encuentra el carácter, se devuelve un valor de –1.  
  
 En el ejemplo siguiente se usa el método **IndexOf** para buscar la primera aparición del carácter '`l`' en una cadena.  
  
 [!code-cpp[Conceptual.String.BasicOps#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#13)]
 [!code-csharp[Conceptual.String.BasicOps#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#13)]
 [!code-vb[Conceptual.String.BasicOps#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#13)]  
  
 Con este ejemplo se muestra `2` en la consola.  
  
 El método **String.LastIndexOf** es parecido al método **String.IndexOf** , con la diferencia de que devuelve la posición de la última instancia de un carácter concreto en una cadena. Distingue mayúsculas y minúsculas y utiliza un índice de base cero.  
  
 En el ejemplo siguiente se usa el método **LastIndexOf** para buscar la última aparición del carácter '`l`' en una cadena.  
  
 [!code-cpp[Conceptual.String.BasicOps#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#14)]
 [!code-csharp[Conceptual.String.BasicOps#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#14)]
 [!code-vb[Conceptual.String.BasicOps#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#14)]  
  
 Con este ejemplo se muestra `9` en la consola.  
  
 Los dos métodos resultan útiles si se usan junto con el método **String.Remove** . Se pueden usar los métodos **IndexOf** o **LastIndexOf** para recuperar la posición de un carácter y, a continuación, proporcionar esa posición al método **Remove** para quitar un carácter o una palabra que comience por ese carácter.  
  
## <a name="see-also"></a>Vea también

- [Operaciones básicas de cadenas](basic-string-operations.md)
- [Realizar operaciones de cadenas que no distinguen entre referencias culturales](../globalization-localization/performing-culture-insensitive-string-operations.md)
- [Ordenación de tablas de peso (para .NET en Windows)](https://www.microsoft.com/download/details.aspx?id=10921)
- [Tabla de elementos de intercalación predeterminada Unicode (para .NET Core en macOS y Linux)](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
