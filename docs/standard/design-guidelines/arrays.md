---
description: 'Más información acerca de: Matrices'
title: Matrices
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: 2d919d5e13a03ed1c5d090339f8f0fd9c1a79190
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642452"
---
# <a name="arrays"></a>Matrices

✔️ Recomendamos usar colecciones en vez de matrices en las API públicas. En la sección [Colecciones](guidelines-for-collections.md) se proporciona información sobre cómo elegir entre colecciones y matrices.

 ❌ NO utilice campos de matriz de solo lectura. El propio campo es de solo lectura y no se puede cambiar, pero los elementos de la matriz sí.

 ✔️ Recomendamos usar matrices escalonadas en lugar de matrices multidimensionales.

 Una matriz escalonada es una matriz con elementos que también son matrices. Las matrices que componen los elementos pueden tener distintos tamaños, reduciendo el espacio desaprovechado para algunos conjuntos de datos (por ejemplo, una matriz dispersa) en comparación con las matrices multidimensionales. Además, CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que podrían presentar un mejor rendimiento en tiempo de ejecución en algunos escenarios.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- <xref:System.Array>
- [Instrucciones de diseño de .NET Framework](index.md)
- [Instrucciones de uso](usage-guidelines.md)
