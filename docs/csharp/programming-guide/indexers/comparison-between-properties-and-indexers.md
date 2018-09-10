---
title: Comparación entre propiedades e indizadores (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 3a78b97f2cac1f2c49be03bc351d9b6f4b6438e6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861447"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="3033f-102">Comparación entre propiedades e indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3033f-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="3033f-103">Los indexadores son como propiedades.</span><span class="sxs-lookup"><span data-stu-id="3033f-103">Indexers are like properties.</span></span> <span data-ttu-id="3033f-104">Excepto por las diferencias que se muestran en la tabla siguiente, todas las reglas que se definen para los descriptores de acceso de propiedad se aplican también a los descriptores de acceso de indexador.</span><span class="sxs-lookup"><span data-stu-id="3033f-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="3033f-105">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="3033f-105">Property</span></span>|<span data-ttu-id="3033f-106">Indexador</span><span class="sxs-lookup"><span data-stu-id="3033f-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="3033f-107">Permite que los métodos se llamen como si fueran miembros de datos públicos.</span><span class="sxs-lookup"><span data-stu-id="3033f-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="3033f-108">Permite que se pueda tener acceso a los elementos de una colección interna de un objeto mediante la notación de matriz en el propio objeto.</span><span class="sxs-lookup"><span data-stu-id="3033f-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="3033f-109">Se ha tenido acceso mediante un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="3033f-109">Accessed through a simple name.</span></span>|<span data-ttu-id="3033f-110">Se ha tenido acceso mediante un índice.</span><span class="sxs-lookup"><span data-stu-id="3033f-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="3033f-111">Puede ser un miembro de instancia o estático.</span><span class="sxs-lookup"><span data-stu-id="3033f-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="3033f-112">Debe ser un miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="3033f-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="3033f-113">Un descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) de una propiedad no tiene parámetros.</span><span class="sxs-lookup"><span data-stu-id="3033f-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="3033f-114">Un descriptor de acceso `get` de un indexador tiene la misma lista de parámetros formales que el indexador.</span><span class="sxs-lookup"><span data-stu-id="3033f-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="3033f-115">Un descriptor de acceso [set](../../../csharp/language-reference/keywords/set.md) de una propiedad contiene el parámetro `value` implícito.</span><span class="sxs-lookup"><span data-stu-id="3033f-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="3033f-116">Un descriptor de acceso `set` de un indexador tiene la misma lista de parámetros formales que el indexador, y también para el parámetro [value](../../../csharp/language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="3033f-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="3033f-117">Admite la sintaxis abreviada con [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3033f-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="3033f-118">No admite la sintaxis abreviada.</span><span class="sxs-lookup"><span data-stu-id="3033f-118">Does not support shortened syntax.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3033f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3033f-119">See Also</span></span>

- [<span data-ttu-id="3033f-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3033f-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3033f-121">Indizadores</span><span class="sxs-lookup"><span data-stu-id="3033f-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="3033f-122">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3033f-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
