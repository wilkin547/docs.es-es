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
# <a name="arrays"></a><span data-ttu-id="09e54-102">Matrices</span><span class="sxs-lookup"><span data-stu-id="09e54-102">Arrays</span></span>
<span data-ttu-id="09e54-103">**✓ DO** prefieren usar colecciones sobre matrices en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="09e54-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="09e54-104">El [colecciones](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sección proporcionan detalles sobre cómo elegir entre las colecciones y matrices.</span><span class="sxs-lookup"><span data-stu-id="09e54-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="09e54-105">**X DO NOT** usar campos de matriz de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="09e54-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="09e54-106">El propio campo es de solo lectura y no se puede cambiar, pero se pueden cambiar los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="09e54-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="09e54-107">**✓ CONSIDER** con matrices escalonadas en lugar de matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="09e54-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="09e54-108">Una matriz escalonada es una matriz con elementos que también son matrices.</span><span class="sxs-lookup"><span data-stu-id="09e54-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="09e54-109">Las matrices que constituyen los elementos pueden ser de tamaños diferentes, reduciendo el espacio desaprovechado para algunos conjuntos de datos (por ejemplo, una matriz de dispersa) en comparación con las matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="09e54-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="09e54-110">Además, el CLR optimiza las operaciones de índice en las matrices escalonadas, por lo que podrían tener un mejor rendimiento en tiempo de ejecución en algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="09e54-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="09e54-111">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="09e54-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="09e54-112">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="09e54-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e54-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="09e54-113">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="09e54-114">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="09e54-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="09e54-115">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="09e54-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
