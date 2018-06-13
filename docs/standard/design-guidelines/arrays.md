---
title: Matrices
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2945ead7c22b759ce88f6585e2254e9bc540a7ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570411"
---
# <a name="arrays"></a>Matrices
**✓ HACER** prefieren usar colecciones sobre matrices en las API públicas. El [colecciones](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sección proporcionan detalles sobre cómo elegir entre las colecciones y matrices.  
  
 **X DO NOT** usar campos de matriz de solo lectura. El propio campo es de solo lectura y no se puede cambiar, pero se pueden cambiar los elementos de la matriz.  
  
 **✓ Considere la posibilidad de** con matrices escalonadas en lugar de matrices multidimensionales.  
  
 Una matriz escalonada es una matriz con elementos que también son matrices. Las matrices que constituyen los elementos pueden ser de tamaños diferentes, reduciendo el espacio desaprovechado para algunos conjuntos de datos (por ejemplo, una matriz de dispersa) en comparación con las matrices multidimensionales. Además, el CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que podrían tener un mejor rendimiento en tiempo de ejecución en algunos escenarios.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Array>  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
