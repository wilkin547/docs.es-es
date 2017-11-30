---
title: "Asignar nombres a parámetros"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b61f2b56b3b8bab67cec6db68a76916c6d7fa05a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="naming-parameters"></a>Asignar nombres a parámetros
Más allá de la razón obvia de legibilidad, es importante seguir las directrices para los nombres de parámetro porque los parámetros se muestran en la documentación y en el diseñador cuando las herramientas de diseño visual proporcionan Intellisense y la funcionalidad de exploración de clase.  
  
 **✓ HACER** utilice seguir el estilo Camel en los nombres de parámetro.  
  
 **✓ HACER** usar nombres de parámetros descriptivos.  
  
 **✓ Considere la posibilidad de** con nombres basados en el significado de un parámetro en lugar de en el tipo del parámetro.  
  
### <a name="naming-operator-overload-parameters"></a>Nombres de parámetros de sobrecarga de operador  
 **✓ HACER** usar `left` y `right` para nombres de parámetros de sobrecarga de operador binario si no hay ningún significado para los parámetros.  
  
 **✓ HACER** usar `value` para unario sobrecarga de operador nombres de parámetro si no hay ningún significado para los parámetros.  
  
 **✓ Considere la posibilidad de** nombres significativos para el operador de sobrecarga parámetros si ello aumentaría valor significativo.  
  
 **X DO NOT** use abreviaturas o índices numéricos para el operador de sobrecarga nombres de parámetro.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Las directrices de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
