---
title: Matrices
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: d4a1f379a88231654c710b1df7b505316377c915
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741804"
---
# <a name="arrays"></a><span data-ttu-id="656e7-102">Matrices</span><span class="sxs-lookup"><span data-stu-id="656e7-102">Arrays</span></span>
<span data-ttu-id="656e7-103">✔️ prefiere usar colecciones sobre matrices en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="656e7-103">✔️ DO prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="656e7-104">En la sección [colecciones](../../../docs/standard/design-guidelines/guidelines-for-collections.md) se proporcionan detalles sobre cómo elegir entre colecciones y matrices.</span><span class="sxs-lookup"><span data-stu-id="656e7-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>

 <span data-ttu-id="656e7-105">❌ no utilizan campos de matriz de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="656e7-105">❌ DO NOT use read-only array fields.</span></span> <span data-ttu-id="656e7-106">El propio campo es de solo lectura y no se puede cambiar, pero los elementos de la matriz se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="656e7-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>

 <span data-ttu-id="656e7-107">✔️ considere la posibilidad de usar matrices escalonadas en lugar de matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="656e7-107">✔️ CONSIDER using jagged arrays instead of multidimensional arrays.</span></span>

 <span data-ttu-id="656e7-108">Una matriz escalonada es una matriz con elementos que también son matrices.</span><span class="sxs-lookup"><span data-stu-id="656e7-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="656e7-109">Las matrices que componen los elementos pueden tener distintos tamaños, lo que conduce a menos espacio desperdiciado para algunos conjuntos de datos (por ejemplo, una matriz dispersa) en comparación con las matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="656e7-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="656e7-110">Además, CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que podrían presentar un mejor rendimiento en tiempo de ejecución en algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="656e7-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>

 <span data-ttu-id="656e7-111">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="656e7-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="656e7-112">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="656e7-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="656e7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="656e7-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="656e7-114">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="656e7-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="656e7-115">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="656e7-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
