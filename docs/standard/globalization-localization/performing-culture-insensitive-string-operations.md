---
title: "Realizar operaciones de cadenas que no distinguen entre referencias culturales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "asignaciones de mayúsculas y minúsculas"
  - "asignaciones personalizadas de mayúsculas y minúsculas"
  - "referencia cultural, reglas personalizadas de ordenación"
  - "reglas personalizadas de ordenación"
  - "operaciones de cadenas que no tienen en cuenta las referencias culturales, opciones para realizarlas"
  - "referencia cultural, asignaciones personalizadas de mayúsculas y minúsculas"
  - "operaciones de cadenas sin tener en cuenta la referencia cultural, sobrecargas de métodos"
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Realizar operaciones de cadenas que no distinguen entre referencias culturales
La mayoría de los métodos de .NET Framework que realizan operaciones de cadenas que tienen en cuenta las referencias culturales de manera predeterminada, disponen de sobrecargas de método que permiten especificar de forma explícita la referencia cultural que hay que usar, pasando un parámetro <xref:System.Globalization.CultureInfo>.  Estas sobrecargas le permiten eliminar variaciones culturales en las asignaciones de mayúsculas y minúsculas y reglas de ordenación, y garantizan resultados independientes de la referencia cultural.  
  
 Esta sección proporciona los siguientes temas para mostrar cómo realizar operaciones de cadenas que no tienen en cuenta las referencias culturales utilizando métodos de .NET Framework que tienen en cuenta las referencias culturales de manera predeterminada.  
  
## En esta sección  
 [Realizar comparaciones de cadenas que no tienen en cuenta las referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Describe cómo utilizar los métodos <xref:System.String.Compare%2A?displayProperty=fullName> y <xref:System.String.CompareTo%2A?displayProperty=fullName> para realizar comparaciones de cadenas sin tener en cuenta la referencia cultural.  
  
 [Realizar cambios de mayúsculas y minúsculas que no tienen en cuenta las referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Describe cómo utilizar los métodos <xref:System.String.ToUpper%2A?displayProperty=fullName>, <xref:System.String.ToLower%2A?displayProperty=fullName>, <xref:System.Char.ToUpper%2A?displayProperty=fullName> y <xref:System.Char.ToLower%2A?displayProperty=fullName> para realizar los cambios de mayúsculas y minúsculas sin tener en cuenta la referencia cultural.  
  
 [Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Describe cómo utilizar la [clase CaseInsensitiveComparer](frlrfSystemCollectionsCaseInsensitiveComparerClassTopic), la <xref:System.Collections.CaseInsensitiveHashCodeProvider>, la [clase SortedList](frlrfSystemCollectionsSortedListClassTopic), el [método ArrayList.Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx) y el [método CollectionsUtil.CreateCaseInsensitiveHashtable](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic) para realizar operaciones que no tienen en cuenta las referencias culturales en colecciones.  
  
 [Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Describe cómo utilizar los métodos <xref:System.Array.Sort%2A?displayProperty=fullName> y <xref:System.Array.BinarySearch%2A?displayProperty=fullName> para realizar operaciones en matrices sin tener en cuenta la referencia cultural.  
  
## Secciones relacionadas  
 [Operaciones de cadenas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Describe por qué deberían tenerse en cuenta las referencias culturales cuando se realizan operaciones en cadenas, y proporciona directrices sobre cuándo realizar operaciones que tienen en cuenta las referencias culturales y cuándo realizar operaciones que no las tienen en cuenta.