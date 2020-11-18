---
title: Matrices
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: c3545c609b6544e6528bbae08889d0ef20473802
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821611"
---
# <a name="arrays"></a>Matrices
✔️ prefiere usar colecciones sobre matrices en las API públicas. En la sección [colecciones](guidelines-for-collections.md) se proporcionan detalles sobre cómo elegir entre colecciones y matrices.

 ❌ No utilice campos de matriz de solo lectura. El propio campo es de solo lectura y no se puede cambiar, pero los elementos de la matriz se pueden cambiar.

 ✔️ considere la posibilidad de usar matrices escalonadas en lugar de matrices multidimensionales.

 Una matriz escalonada es una matriz con elementos que también son matrices. Las matrices que componen los elementos pueden tener distintos tamaños, lo que conduce a menos espacio desperdiciado para algunos conjuntos de datos (por ejemplo, una matriz dispersa) en comparación con las matrices multidimensionales. Además, CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que podrían presentar un mejor rendimiento en tiempo de ejecución en algunos escenarios.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- <xref:System.Array>
- [Directrices de diseño de marco](index.md)
- [Instrucciones de uso](usage-guidelines.md)
