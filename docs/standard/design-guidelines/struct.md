---
title: "Dise&#241;o de estructura | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "instrucciones de diseño clases biblioteca [.NET Framework], estructuras"
  - "desasignar estructuras"
  - "asignar estructuras"
  - "tipos de valor, estructuras"
  - "diseño de estructura"
  - "Escriba las instrucciones de diseño de estructuras"
  - "estructuras [.NET Framework], instrucciones de diseño"
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Dise&#241;o de estructura
El tipo de valor de propósito general más a menudo se denomina un struct, la palabra clave de C\#. Esta sección proporciona instrucciones para el diseño de la estructura general.  
  
 **X no** proporcionar un constructor predeterminado para una estructura.  
  
 Cumplimiento de esta instrucción permite matrices de estructuras se pueden crear sin tener que ejecutar el constructor en cada elemento de la matriz. Tenga en cuenta que C\# no permite estructuras tengan constructores predeterminados.  
  
 **X no** definir tipos de valor mutable.  
  
 Tipos de valor mutable tienen varios problemas. Por ejemplo, cuando un captador de propiedad devuelve un tipo de valor, el llamador recibe una copia. Dado que la copia se crea implícitamente, los desarrolladores no sea conscientes de que mutación de la copia y no el valor original. Además, algunos lenguajes \(lenguajes dinámicos en particular\) tienen problemas con tipos de valor mutable porque incluso las variables locales, cuando se desreferencia, hacer una copia de realizarse.  
  
 **✓ hacer** asegurarse de que un estado donde todos los datos de la instancia se establece en cero, false o null \(según corresponda\) es válido.  
  
 Esto evita la creación accidental de instancias no válidas cuando se crea una matriz de las estructuras.  
  
 **✓ hacer** implementar <xref:System.IEquatable%601> en tipos de valor.  
  
 El <xref:System.Object.Equals%2A?displayProperty=fullName> método en tipos de valor provoca la conversión boxing y la implementación predeterminada no es muy eficaz, porque se usa la reflexión.<xref:System.IEquatable%601.Equals%2A> puede tener un rendimiento mucho mejor y se puede implementar de manera que no causen conversión boxing.  
  
 **X no** extender explícitamente <xref:System.ValueType>. De hecho, la mayoría de los lenguajes evitar esto.  
  
 En general, las estructuras pueden ser muy útiles, pero sólo se deben utilizar para los valores inmutables, únicos y pequeños que no se aplicar la conversión boxing con frecuencia.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Elegir entre clases y structs](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)