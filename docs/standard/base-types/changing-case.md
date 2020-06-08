---
title: Cambiar mayúsculas y minúsculas en .NET
description: Obtenga información sobre cómo cambiar las mayúsculas y minúsculas en .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework], case
- case sensitivity
- ToUpper method
- ToLower method
- uppercase
- lowercase
ms.assetid: 6805f81b-e9ad-4387-9f4c-b9bdb21b87c0
ms.openlocfilehash: e838d6df778802d7eaab3f12205698cc6ca5f72b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290596"
---
# <a name="change-case-in-net"></a>Cambio de mayúsculas y minúsculas en .NET

Si escribe una aplicación que acepta la entrada de un usuario, nunca podrá estar seguro de si usará mayúsculas o minúsculas para escribir los datos. Normalmente querrá que las cadenas usen mayúsculas y minúsculas de forma coherente, especialmente si se van a mostrar en la interfaz de usuario. En la tabla siguiente se describen tres métodos para cambiar las mayúsculas y minúsculas. Los dos primeros métodos proporcionan una sobrecarga que acepta una referencia cultural.  
  
|Nombre del método|Usar|  
|-----------------|---------|  
|<xref:System.String.ToUpper%2A?displayProperty=nameWithType>|Convierte todos los caracteres de una cadena a mayúsculas.|  
|<xref:System.String.ToLower%2A?displayProperty=nameWithType>|Convierte todos los caracteres de una cadena a minúsculas.|  
|<xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType>|Convierte una cadena a mayúsculas de tipo título.|  
  
> [!WARNING]
> Tenga en cuenta que los métodos <xref:System.String.ToUpper%2A?displayProperty=nameWithType> y <xref:System.String.ToLower%2A?displayProperty=nameWithType> no deben usarse para convertir cadenas para compararlas ni para comprobar su igualdad. Para más información, vea la sección [Comparar cadenas con mayúsculas y minúsculas mezcladas](#Comparing).  
  
<a name="Comparing"></a>
## <a name="compare-strings-of-mixed-case"></a>Comparación de cadenas con mayúsculas y minúsculas mezcladas  

 Para comparar cadenas con mayúsculas y minúsculas mezcladas para determinar su orden, llame a una de las sobrecargas del método <xref:System.String.CompareTo%2A?displayProperty=nameWithType> con un parámetro `comparisonType` y proporcione un valor <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType>, <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> o <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> para el argumento `comparisonType`. Para realizar una comparación usando una referencia cultural específica que no sea la referencia cultural actual, llame a una sobrecarga del método <xref:System.String.CompareTo%2A?displayProperty=nameWithType> con los parámetros `culture` y `options`, y proporcione el valor <xref:System.Globalization.CompareOptions.IgnoreCase?displayProperty=nameWithType> como el argumento `options`.  
  
 Para comparar cadenas con mayúsculas y minúsculas mezcladas para determinar si son iguales, llame a una de las sobrecargas del método <xref:System.String.Equals%2A?displayProperty=nameWithType> con un parámetro `comparisonType` y proporcione un valor <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType>, <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> o <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> para el argumento `comparisonType`.  
  
 Para obtener más información, consulte [Procedimientos recomendados para el uso de cadenas](best-practices-strings.md).  
  
## <a name="toupper"></a>ToUpper  
 El método <xref:System.String.ToUpper%2A?displayProperty=nameWithType> convierte todos los caracteres de una cadena a mayúsculas. En el siguiente ejemplo, se convierte la cadena "Hello World!" de mayúsculas y minúsculas mezcladas a mayúsculas.  
  
 [!code-csharp[Strings.ChangingCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#1)]
 [!code-vb[Strings.ChangingCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#1)]  
  
 El ejemplo anterior tiene en cuenta la referencia cultural de forma predeterminada; aplica las convenciones de mayúsculas y minúsculas de la referencia cultural actual. Para realizar un cambio de mayúsculas y minúsculas sin tener en cuenta la referencia cultural o para aplicar las convenciones de mayúsculas y minúsculas de una referencia cultural determinada, use la sobrecarga del método <xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType> y proporcione un valor <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> o un objeto <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> que representa la referencia cultural especificada al parámetro *culture*. Para obtener un ejemplo que muestra cómo usar el método <xref:System.String.ToUpper%2A> para realizar un cambio de mayúsculas y minúsculas sin tener en cuenta la referencia cultural, consulte [Realizar cambios de mayúsculas y minúsculas que no tienen en cuenta las referencias culturales](../globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## <a name="tolower"></a>ToLower  
 El método <xref:System.String.ToLower%2A?displayProperty=nameWithType> es similar al método anterior, pero en su lugar convierte todos los caracteres de una cadena a minúsculas. En el siguiente ejemplo, se convierte la cadena "Hello World!" en minúsculas.  
  
 [!code-csharp[Strings.ChangingCase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#2)]
 [!code-vb[Strings.ChangingCase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#2)]  
  
 El ejemplo anterior tiene en cuenta la referencia cultural de forma predeterminada; aplica las convenciones de mayúsculas y minúsculas de la referencia cultural actual. Para realizar un cambio de mayúsculas y minúsculas sin tener en cuenta la referencia cultural o para aplicar las convenciones de mayúsculas y minúsculas de una referencia cultural determinada, use la sobrecarga del método <xref:System.String.ToLower%28System.Globalization.CultureInfo%29?displayProperty=nameWithType> y proporcione un valor <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> o un objeto <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> que representa la referencia cultural especificada al parámetro *culture*. Para obtener un ejemplo que muestra cómo usar el método <xref:System.String.ToLower%28System.Globalization.CultureInfo%29> para realizar un cambio de mayúsculas y minúsculas sin tener en cuenta la referencia cultural, consulte [Realizar cambios de mayúsculas y minúsculas que no tienen en cuenta las referencias culturales](../globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## <a name="totitlecase"></a>ToTitleCase  
 El método <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType> convierte el primer carácter de cada palabra a mayúsculas y el resto de los caracteres a minúsculas. Sin embargo, se da por hecho que las palabras que están completamente en mayúsculas son siglas y no se convierten.  
  
 El método <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType> tiene en cuenta la referencia cultural; es decir, usa las convenciones de mayúsculas y minúsculas de una referencia cultural determinada. Para llamar al método, recupere primero el objeto <xref:System.Globalization.TextInfo> que representa las convenciones de mayúsculas y minúsculas de la referencia cultural determinada a partir de la propiedad <xref:System.Globalization.CultureInfo.TextInfo%2A?displayProperty=nameWithType> de una referencia cultural determinada.  
  
 En el ejemplo siguiente, se pasa cada cadena de una matriz al método <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType>.  Las cadenas incluyen cadenas de título correctas así como acrónimos. Las cadenas se convierten a mayúsculas de tipo título usando las convenciones de mayúsculas y minúsculas de la referencia cultural Inglés (Estados Unidos).  
  
 [!code-csharp[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/cs/totitlecase2.cs#1)]
 [!code-vb[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/vb/totitlecase2.vb#1)]  
  
 Recuerde que, aunque tiene en cuenta la referencia cultural, el método <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType> no proporciona reglas de mayúsculas y minúsculas lingüísticamente correctas. En el ejemplo anterior, el método convierte "a tale of two cities" en "A Tale Of Two Cities". Sin embargo, el uso lingüísticamente correcto de las mayúsculas y minúsculas de título para la referencia cultural en-US es "A Tale of Two Cities".  
  
## <a name="see-also"></a>Vea también

- [Operaciones básicas de cadenas](basic-string-operations.md)
- [Realizar operaciones de cadenas que no distinguen entre referencias culturales](../globalization-localization/performing-culture-insensitive-string-operations.md)
