---
title: 'Comparación entre propiedades e indizadores: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 330d222083ce599719698c023803196dfe88da84
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712135"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="80531-102">Comparación entre propiedades e indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="80531-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="80531-103">Los indexadores son como propiedades.</span><span class="sxs-lookup"><span data-stu-id="80531-103">Indexers are like properties.</span></span> <span data-ttu-id="80531-104">Excepto por las diferencias que se muestran en la tabla siguiente, todas las reglas que se definen para los descriptores de acceso de propiedad se aplican también a los descriptores de acceso de indexador.</span><span class="sxs-lookup"><span data-stu-id="80531-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="80531-105">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="80531-105">Property</span></span>|<span data-ttu-id="80531-106">Indexador</span><span class="sxs-lookup"><span data-stu-id="80531-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="80531-107">Permite que los métodos se llamen como si fueran miembros de datos públicos.</span><span class="sxs-lookup"><span data-stu-id="80531-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="80531-108">Permite que se pueda tener acceso a los elementos de una colección interna de un objeto mediante la notación de matriz en el propio objeto.</span><span class="sxs-lookup"><span data-stu-id="80531-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="80531-109">Se ha tenido acceso mediante un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="80531-109">Accessed through a simple name.</span></span>|<span data-ttu-id="80531-110">Se ha tenido acceso mediante un índice.</span><span class="sxs-lookup"><span data-stu-id="80531-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="80531-111">Puede ser un miembro de instancia o estático.</span><span class="sxs-lookup"><span data-stu-id="80531-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="80531-112">Debe ser un miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="80531-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="80531-113">Un descriptor de acceso [get](../../language-reference/keywords/get.md) de una propiedad no tiene parámetros.</span><span class="sxs-lookup"><span data-stu-id="80531-113">A [get](../../language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="80531-114">Un descriptor de acceso `get` de un indexador tiene la misma lista de parámetros formales que el indexador.</span><span class="sxs-lookup"><span data-stu-id="80531-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="80531-115">Un descriptor de acceso [set](../../language-reference/keywords/set.md) de una propiedad contiene el parámetro `value` implícito.</span><span class="sxs-lookup"><span data-stu-id="80531-115">A [set](../../language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="80531-116">Un descriptor de acceso `set` de un indexador tiene la misma lista de parámetros formales que el indexador, y también para el parámetro [value](../../language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="80531-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="80531-117">Admite la sintaxis abreviada con [Propiedades autoimplementadas](../classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="80531-117">Supports shortened syntax with [Auto-Implemented Properties](../classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="80531-118">Admite miembros de cuerpo de expresión para obtener solo indexadores.</span><span class="sxs-lookup"><span data-stu-id="80531-118">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80531-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="80531-119">See also</span></span>

- [<span data-ttu-id="80531-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="80531-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="80531-121">Indizadores</span><span class="sxs-lookup"><span data-stu-id="80531-121">Indexers</span></span>](./index.md)
- [<span data-ttu-id="80531-122">Propiedades</span><span class="sxs-lookup"><span data-stu-id="80531-122">Properties</span></span>](../classes-and-structs/properties.md)
