---
title: "Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices | Microsoft Docs"
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
  - "matrices [.NET Framework], operaciones de cadena que no tienen en cuenta la referencia cultural"
  - "parámetro de comparación"
  - "operaciones de cadena que no tienen en cuenta la referencia cultural, en matrices"
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices
De forma predeterminada, las sobrecargas de los métodos <xref:System.Array.Sort%2A?displayProperty=fullName> y <xref:System.Array.BinarySearch%2A?displayProperty=fullName> realizan las ordenaciones dependientes de la referencia cultural mediante la propiedad <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName>.  Los resultados que tienen en cuenta las referencias culturales devueltas por estos métodos pueden cambiar en función de las referencias culturales debido a las diferencias en los criterios de ordenación.  Para eliminar el comportamiento dependiente de la referencia cultural, use una de las sobrecargas de este método que acepte un parámetro `comparer`.  El parámetro `comparer` especifica la implementación de <xref:System.Collections.IComparer> que se va a usar al comparar elementos de la matriz.  Para el parámetro, especifique una clase comparadora invariable personalizada que use <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  Hay un ejemplo de una clase comparadora invariable personalizada en el subtema "Utilizar la clase SortedList" del tema [Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md).  
  
 **Nota** Al pasar **CultureInfo.InvariantCulture** a un método de comparación, se realiza una comparación independiente de la referencia cultural.  Sin embargo, no se realiza una comparación no lingüística, por ejemplo, para las rutas de acceso a archivos, las claves del Registro y las variables de entorno.  Tampoco se admiten decisiones de seguridad basadas en el resultado de la comparación.  Para que se realice una comparación no lingüística o se admitan decisiones de seguridad basadas en los resultados, la aplicación debe usar un método de comparación que acepte un valor de <xref:System.StringComparison>.  A continuación, la aplicación debe pasar <xref:System.StringComparison>.  
  
## Vea también  
 <xref:System.Array.Sort%2A?displayProperty=fullName>   
 <xref:System.Array.BinarySearch%2A?displayProperty=fullName>   
 <xref:System.Collections.IComparer>   
 [Realizar operaciones de cadenas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)