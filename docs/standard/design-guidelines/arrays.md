---
title: Matrices
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: KrzysztofCwalina
ms.openlocfilehash: dd30cdee0440553a9f955f0b3f4ee420e938b9ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864122"
---
# <a name="arrays"></a>Matrices
**✓ DO** prefieren usar colecciones sobre matrices en las API públicas. El [colecciones](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sección proporcionan detalles sobre cómo elegir entre las colecciones y matrices.  
  
 **X DO NOT** usar campos de matriz de solo lectura. El propio campo es de solo lectura y no se puede cambiar, pero se pueden cambiar los elementos de la matriz.  
  
 **✓ CONSIDER** con matrices escalonadas en lugar de matrices multidimensionales.  
  
 Una matriz escalonada es una matriz con elementos que también son matrices. Las matrices que constituyen los elementos pueden ser de tamaños diferentes, dando lugar a espacio desaprovechado para algunos conjuntos de datos (por ejemplo, la matriz dispersa) en comparación con las matrices multidimensionales. Además, el CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que es posible que presentan un mejor rendimiento en tiempo de ejecución en algunos escenarios.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- <xref:System.Array>
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
