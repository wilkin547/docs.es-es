---
title: Realizar comparaciones de cadenas que no tienen en cuenta las referencias culturales
ms.date: 08/22/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.CompareTo method
- String.Compare method
- string comparison [.NET Framework], culture-insensitive
- strings [.NET Framework], comparing
- culture-insensitive string operations, comparisons
- culture parameter
ms.assetid: abae50ef-32f7-4a50-a540-fd256fd1aed0
ms.openlocfilehash: 85ba91b63ab0edbccc768e2d1ad4aaef31fd2f21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120830"
---
# <a name="performing-culture-insensitive-string-comparisons"></a>Realizar comparaciones de cadenas que no tienen en cuenta las referencias culturales
De manera predeterminada, el método <xref:System.String.Compare%2A?displayProperty=nameWithType> realiza comparaciones que tienen en cuenta las referencias culturales y las mayúsculas y minúsculas. Este método también incluye varias sobrecargas que proporcionan un parámetro `culture` que permite especificar la referencia cultural que se va a utilizar y un parámetro `comparisonType` que permite especificar las reglas de comparación que se van a usar. Al llamar a estos métodos en lugar de a la sobrecarga predeterminada, se quita cualquier ambigüedad sobre las reglas que se utilizan en una determinada llamada al método y se establece claramente si una determinada comparación tiene en cuenta o no la referencia cultural.  
  
> [!NOTE]
> Las dos sobrecargas del método <xref:System.String.CompareTo%2A?displayProperty=nameWithType> realizan comparaciones que tienen en cuenta la referencia cultural y que distinguen mayúsculas de minúsculas, así que no puede usar este método para realizar comparaciones que no tengan en cuenta la referencia cultural. Para lograr claridad en el código, recomendamos utilizar el método <xref:System.String.Compare%2A?displayProperty=nameWithType> en su lugar.  
  
 En operaciones que tienen en cuenta las referencias culturales, especifique el valor de enumeración <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType> o <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> como parámetro `comparisonType`. Si desea realizar una comparación que tenga en cuenta la referencia cultural utilizando una referencia cultural designada distinta de la referencia cultural actual, especifique el objeto <xref:System.Globalization.CultureInfo> que representa esa referencia cultural como parámetro `culture`.  
  
 Las comparaciones de cadenas que no tienen en cuenta la referencia cultural admitidas por el método <xref:System.String.Compare%2A?displayProperty=nameWithType> pueden ser lingüísticas (se basan en las convenciones de ordenación de la referencia cultural de todos los idiomas) o no lingüísticas (se basan en el valor ordinal de los caracteres de la cadena). La mayoría de las comparaciones de cadenas que no tienen en cuenta la referencia cultural son no lingüísticas. En estas comparaciones, especifique el valor de enumeración <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> u <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> como parámetro `comparisonType`. Por ejemplo, si una decisión de seguridad (como una comparación de nombre de usuario o contraseña) está basada en el resultado de una comparación de cadenas, la operación no debe tener en cuenta la referencia cultural y debe ser no lingüística para garantizar que el resultado no se ve afectado por las convenciones de una determinada referencia cultural o idioma.  
  
 Utilice una comparación de cadenas de tipo lingüística y que tenga en cuenta la referencia cultural si desea administrar lingüísticamente las cadenas pertinentes de varias referencias culturales de forma coherente. Por ejemplo, si la aplicación muestra palabras que utilizan varios juegos de caracteres en un cuadro de lista, tal vez desee mostrar las palabras en el mismo orden sin tener en cuenta la referencia cultural actual. En las comparaciones lingüísticas que no tienen en cuenta la referencia cultural, .NET Framework define una referencia cultural de todos los idiomas que está basada en las convenciones lingüísticas del inglés. Para realizar una comparación lingüística que no tenga en cuenta la referencia cultural, especifique <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> o <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> como parámetro `comparisonType`.  
  
 En el siguiente ejemplo se realizan dos comparaciones de cadenas no lingüísticas que no tienen en cuenta la referencia cultural. La primera comparación distingue mayúsculas de minúsculas, pero la segunda no.  
  
 [!code-csharp[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/cs/cultureinsensitive1.cs#1)]
 [!code-vb[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/vb/cultureinsensitive1.vb#1)]  

Puede descargar las [tablas de pesos de ordenación](https://www.microsoft.com/download/details.aspx?id=10921), un conjunto de archivos de texto que contienen información sobre los pesos de caracteres que se usan en las operaciones de ordenación y comparación para los sistemas operativos Windows, además de la [tabla de elementos de intercalación Unicode predeterminada](https://www.unicode.org/Public/UCA/latest/allkeys.txt), que se trata de la tabla de pesos de ordenación para Linux y macOS.

## <a name="see-also"></a>Vea también

- <xref:System.String.Compare%2A?displayProperty=nameWithType>
- <xref:System.String.CompareTo%2A?displayProperty=nameWithType>
- [Realizar operaciones de cadenas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
- [Procedimientos recomendados para el uso de cadenas](../../../docs/standard/base-types/best-practices-strings.md)
