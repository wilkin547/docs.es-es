---
title: Asignar nombres a parámetros
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: KrzysztofCwalina
ms.openlocfilehash: 0e5b33839372e303b96bd6b84949f9a82da2f689
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646625"
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
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
