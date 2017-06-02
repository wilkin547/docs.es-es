---
title: "Matrices | Microsoft Docs"
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
  - "instrucciones de diseño clase biblioteca [.NET Framework], matrices"
  - "matrices [.NET Framework], instrucciones de uso"
  - "matrices vacías"
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Matrices
**✓ hacer** prefieren usar colecciones en las matrices en las API públicas. El [Colecciones](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sección proporciona detalles acerca de cómo elegir entre colecciones y matrices.  
  
 **X no** utilizar campos de matriz de sólo lectura. El campo es de solo lectura y no se puede cambiar, pero se pueden cambiar los elementos de la matriz.  
  
 **✓, considere la posibilidad de** mediante matrices escalonadas en lugar de matrices multidimensionales.  
  
 Una matriz escalonada es una matriz con elementos que también son matrices. Las matrices que constituyen los elementos pueden ser de tamaños diferentes, reduciendo el espacio desaprovechado para algunos conjuntos de datos \(por ejemplo, una matriz dispersa\) en comparación con las matrices multidimensionales. Además, CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que podrían tener un mejor rendimiento en tiempo de ejecución en algunos escenarios.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 <xref:System.Array>   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)