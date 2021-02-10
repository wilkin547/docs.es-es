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
# <a name="arrays"></a><span data-ttu-id="a75ac-103">Matrices</span><span class="sxs-lookup"><span data-stu-id="a75ac-103">Arrays</span></span>

<span data-ttu-id="a75ac-104">✔️ Recomendamos usar colecciones en vez de matrices en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="a75ac-104">✔️ DO prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="a75ac-105">En la sección [Colecciones](guidelines-for-collections.md) se proporciona información sobre cómo elegir entre colecciones y matrices.</span><span class="sxs-lookup"><span data-stu-id="a75ac-105">The [Collections](guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>

 <span data-ttu-id="a75ac-106">❌ NO utilice campos de matriz de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a75ac-106">❌ DO NOT use read-only array fields.</span></span> <span data-ttu-id="a75ac-107">El propio campo es de solo lectura y no se puede cambiar, pero los elementos de la matriz sí.</span><span class="sxs-lookup"><span data-stu-id="a75ac-107">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>

 <span data-ttu-id="a75ac-108">✔️ Recomendamos usar matrices escalonadas en lugar de matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="a75ac-108">✔️ CONSIDER using jagged arrays instead of multidimensional arrays.</span></span>

 <span data-ttu-id="a75ac-109">Una matriz escalonada es una matriz con elementos que también son matrices.</span><span class="sxs-lookup"><span data-stu-id="a75ac-109">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="a75ac-110">Las matrices que componen los elementos pueden tener distintos tamaños, reduciendo el espacio desaprovechado para algunos conjuntos de datos (por ejemplo, una matriz dispersa) en comparación con las matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="a75ac-110">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="a75ac-111">Además, CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que podrían presentar un mejor rendimiento en tiempo de ejecución en algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="a75ac-111">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>

 <span data-ttu-id="a75ac-112">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="a75ac-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a75ac-113">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="a75ac-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a75ac-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a75ac-114">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="a75ac-115">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a75ac-115">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="a75ac-116">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="a75ac-116">Usage Guidelines</span></span>](usage-guidelines.md)
