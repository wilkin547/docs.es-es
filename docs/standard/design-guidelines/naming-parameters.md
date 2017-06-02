---
title: "Nomenclatura de par&#225;metros | Microsoft Docs"
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
  - "parámetros, nombres"
  - "nombres [.NET Framework], parámetros"
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Nomenclatura de par&#225;metros
Más allá de la razón obvia de legibilidad, es importante seguir las directrices para los nombres de parámetro porque los parámetros se muestran en la documentación y en el diseñador cuando las herramientas de diseño visual proporcionan Intellisense y la funcionalidad de exploración de clase.  
  
 **✓ hacer** camelCasing se utiliza en nombres de parámetro.  
  
 **✓ hacer** utilizar nombres de parámetros descriptivos.  
  
 **✓ considere** con nombres basados en el significado de un parámetro en lugar de en el tipo del parámetro.  
  
### Nombres de parámetros de sobrecarga de operador  
 **✓ hacer** use `left` y `right` para nombres de parámetros de sobrecarga de operador binario si no tiene ningún significado para los parámetros.  
  
 **✓ hacer** use `value` para unario sobrecarga de operador nombres de parámetro si no tiene ningún significado para los parámetros.  
  
 **✓ considere** nombres significativos para el operador de sobrecarga parámetros si hacerlo implica un valor significativo.  
  
 **X no** use abreviaturas o índices numéricos para el operador de sobrecarga nombres de parámetro.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)