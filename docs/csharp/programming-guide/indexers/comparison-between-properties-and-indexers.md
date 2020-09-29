---
title: 'Comparación entre propiedades e indizadores: Guía de programación de C#'
description: Compare el modo en que los indexadores en C# se parecen a las propiedades. Excepto por algunas diferencias, las reglas que se definen para los descriptores de acceso de propiedad se aplican a los descriptores de acceso de indexador.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: fff20ca965e7614d26f7da32321a829d13292389
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192534"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="57da4-104">Comparación entre propiedades e indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="57da4-104">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="57da4-105">Los indexadores son como propiedades.</span><span class="sxs-lookup"><span data-stu-id="57da4-105">Indexers are like properties.</span></span> <span data-ttu-id="57da4-106">Excepto por las diferencias que se muestran en la tabla siguiente, todas las reglas que se definen para los descriptores de acceso de propiedad se aplican también a los descriptores de acceso de indexador.</span><span class="sxs-lookup"><span data-stu-id="57da4-106">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="57da4-107">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="57da4-107">Property</span></span>|<span data-ttu-id="57da4-108">Indexador</span><span class="sxs-lookup"><span data-stu-id="57da4-108">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="57da4-109">Permite que los métodos se llamen como si fueran miembros de datos públicos.</span><span class="sxs-lookup"><span data-stu-id="57da4-109">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="57da4-110">Permite que se pueda tener acceso a los elementos de una colección interna de un objeto mediante la notación de matriz en el propio objeto.</span><span class="sxs-lookup"><span data-stu-id="57da4-110">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="57da4-111">Se ha tenido acceso mediante un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="57da4-111">Accessed through a simple name.</span></span>|<span data-ttu-id="57da4-112">Se ha tenido acceso mediante un índice.</span><span class="sxs-lookup"><span data-stu-id="57da4-112">Accessed through an index.</span></span>|  
|<span data-ttu-id="57da4-113">Puede ser un miembro de instancia o estático.</span><span class="sxs-lookup"><span data-stu-id="57da4-113">Can be a static or an instance member.</span></span>|<span data-ttu-id="57da4-114">Debe ser un miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="57da4-114">Must be an instance member.</span></span>|  
|<span data-ttu-id="57da4-115">Un descriptor de acceso [get](../../language-reference/keywords/get.md) de una propiedad no tiene parámetros.</span><span class="sxs-lookup"><span data-stu-id="57da4-115">A [get](../../language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="57da4-116">Un descriptor de acceso `get` de un indexador tiene la misma lista de parámetros formales que el indexador.</span><span class="sxs-lookup"><span data-stu-id="57da4-116">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="57da4-117">Un descriptor de acceso [set](../../language-reference/keywords/set.md) de una propiedad contiene el parámetro `value` implícito.</span><span class="sxs-lookup"><span data-stu-id="57da4-117">A [set](../../language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="57da4-118">Un descriptor de acceso `set` de un indexador tiene la misma lista de parámetros formales que el indexador, y también para el parámetro [value](../../language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="57da4-118">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="57da4-119">Admite la sintaxis abreviada con [Propiedades autoimplementadas](../classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="57da4-119">Supports shortened syntax with [Auto-Implemented Properties](../classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="57da4-120">Admite miembros de cuerpo de expresión para obtener solo indexadores.</span><span class="sxs-lookup"><span data-stu-id="57da4-120">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57da4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57da4-121">See also</span></span>

- [<span data-ttu-id="57da4-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="57da4-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="57da4-123">Indizadores</span><span class="sxs-lookup"><span data-stu-id="57da4-123">Indexers</span></span>](./index.md)
- [<span data-ttu-id="57da4-124">Propiedades</span><span class="sxs-lookup"><span data-stu-id="57da4-124">Properties</span></span>](../classes-and-structs/properties.md)
