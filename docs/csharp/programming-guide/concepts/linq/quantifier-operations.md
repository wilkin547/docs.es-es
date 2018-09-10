---
title: Operaciones cuantificadoras (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 24c8f9a6b589592c26c8a514bc44ff9623a82d2f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523110"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="b2641-102">Operaciones cuantificadoras (C#)</span><span class="sxs-lookup"><span data-stu-id="b2641-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="b2641-103">Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="b2641-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="b2641-104">En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="b2641-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="b2641-105">La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="b2641-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="b2641-106">La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="b2641-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="b2641-107">![Operaciones cuantificadoras en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="b2641-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="b2641-108">Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="b2641-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2641-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="b2641-109">Methods</span></span>  
  
|<span data-ttu-id="b2641-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="b2641-110">Method Name</span></span>|<span data-ttu-id="b2641-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2641-111">Description</span></span>|<span data-ttu-id="b2641-112">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="b2641-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="b2641-113">Más información</span><span class="sxs-lookup"><span data-stu-id="b2641-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="b2641-114">Todas</span><span class="sxs-lookup"><span data-stu-id="b2641-114">All</span></span>|<span data-ttu-id="b2641-115">Determina si todos los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="b2641-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="b2641-116">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="b2641-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b2641-117">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="b2641-117">Any</span></span>|<span data-ttu-id="b2641-118">Determina si algunos de los elementos de una secuencia cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="b2641-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="b2641-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="b2641-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b2641-120">Contiene</span><span class="sxs-lookup"><span data-stu-id="b2641-120">Contains</span></span>|<span data-ttu-id="b2641-121">Determina si una secuencia contiene un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="b2641-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="b2641-122">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="b2641-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="b2641-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2641-123">See Also</span></span>

- <xref:System.Linq>  
- <span data-ttu-id="b2641-124">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)(Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="b2641-124">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>  
- [<span data-ttu-id="b2641-125">Cómo: Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b2641-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
- [<span data-ttu-id="b2641-126">Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b2641-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
