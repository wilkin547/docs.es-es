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
ms.openlocfilehash: 1ac7e28c3172f2ed68d402e1d04a1664644c7f25
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48024537"
---
# <a name="arrays"></a>Matrices
**✓ DO** prefieren usar colecciones sobre matrices en las API públicas. El [colecciones](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sección proporcionan detalles sobre cómo elegir entre las colecciones y matrices.  
  
 **X DO NOT** usar campos de matriz de solo lectura. El propio campo es de solo lectura y no se puede cambiar, pero se pueden cambiar los elementos de la matriz.  
  
 **✓ CONSIDER** con matrices escalonadas en lugar de matrices multidimensionales.  
  
 Una matriz escalonada es una matriz con elementos que también son matrices. Las matrices que constituyen los elementos pueden ser de tamaños diferentes, dando lugar a espacio desaprovechado para algunos conjuntos de datos (por ejemplo, la matriz dispersa) en comparación con las matrices multidimensionales. Además, el CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que es posible que presentan un mejor rendimiento en tiempo de ejecución en algunos escenarios.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- <xref:System.Array>  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
