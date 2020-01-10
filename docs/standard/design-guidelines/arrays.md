---
title: Matrices
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: ac4b073d2d3291922498a0e56c7e81f7e7868c65
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709574"
---
# <a name="arrays"></a><span data-ttu-id="d7ecf-102">Matrices</span><span class="sxs-lookup"><span data-stu-id="d7ecf-102">Arrays</span></span>
<span data-ttu-id="d7ecf-103">**✓ DO** prefieren usar colecciones sobre matrices en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="d7ecf-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="d7ecf-104">En la sección [colecciones](../../../docs/standard/design-guidelines/guidelines-for-collections.md) se proporcionan detalles sobre cómo elegir entre colecciones y matrices.</span><span class="sxs-lookup"><span data-stu-id="d7ecf-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="d7ecf-105">**X DO NOT** usar campos de matriz de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="d7ecf-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="d7ecf-106">El propio campo es de solo lectura y no se puede cambiar, pero los elementos de la matriz se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="d7ecf-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="d7ecf-107">**✓ CONSIDER** con matrices escalonadas en lugar de matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="d7ecf-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="d7ecf-108">Una matriz escalonada es una matriz con elementos que también son matrices.</span><span class="sxs-lookup"><span data-stu-id="d7ecf-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="d7ecf-109">Las matrices que componen los elementos pueden tener distintos tamaños, lo que conduce a menos espacio desperdiciado para algunos conjuntos de datos (por ejemplo, una matriz dispersa) en comparación con las matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="d7ecf-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="d7ecf-110">Además, CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que podrían presentar un mejor rendimiento en tiempo de ejecución en algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="d7ecf-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="d7ecf-111">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="d7ecf-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d7ecf-112">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="d7ecf-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ecf-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7ecf-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="d7ecf-114">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d7ecf-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="d7ecf-115">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="d7ecf-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
