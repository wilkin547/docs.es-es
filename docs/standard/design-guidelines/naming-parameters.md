---
title: Asignar nombres a parámetros
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e6a8a1dcdcb8fa3311b040c72987f0f76e681fc
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086477"
---
# <a name="naming-parameters"></a>Asignar nombres a parámetros
Más allá de la razón obvia de legibilidad, es importante seguir las instrucciones para los nombres de parámetro porque los parámetros se muestran en la documentación y en el diseñador cuando las herramientas de diseño visual proporcionan Intellisense y la funcionalidad de exploración de clase.  
  
 **✓ DO** utilice seguir el estilo Camel en los nombres de parámetro.  
  
 **✓ DO** usar nombres de parámetros descriptivos.  
  
 **✓ CONSIDER** con nombres basados en el significado de un parámetro en lugar de en el tipo del parámetro.  
  
### <a name="naming-operator-overload-parameters"></a>Asignar nombres a parámetros de sobrecarga de operador  
 **✓ DO** usar `left` y `right` para nombres de parámetros de sobrecarga de operador binario si no hay ningún significado para los parámetros.  
  
 **✓ DO** usar `value` para unario sobrecarga de operador nombres de parámetro si no hay ningún significado para los parámetros.  
  
 **✓ CONSIDER** nombres significativos para el operador de sobrecarga parámetros si ello aumentaría valor significativo.  
  
 **X DO NOT** use abreviaturas o índices numéricos para el operador de sobrecarga nombres de parámetro.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
