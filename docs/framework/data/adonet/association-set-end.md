---
title: extremo del conjunto de asociaciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 20810eddda98403d244f6104807504489dde71cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="association-set-end"></a><span data-ttu-id="a2754-102">extremo del conjunto de asociaciones</span><span class="sxs-lookup"><span data-stu-id="a2754-102">association set end</span></span>
<span data-ttu-id="a2754-103">Un *final del conjunto de asociaciones* identifica el [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) y [conjunto de entidades](../../../../docs/framework/data/adonet/entity-set.md) al final de un [conjunto de asociaciones](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="a2754-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="a2754-104">Los extremos de conjuntos de asociaciones se definen como parte de un conjunto de asociaciones, que debe tener exactamente dos extremos.</span><span class="sxs-lookup"><span data-stu-id="a2754-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="a2754-105">Una definición de extremo de conjunto de asociaciones contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2754-105">An association set end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="a2754-106">Uno de los tipos de entidad implicados en el conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="a2754-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="a2754-107">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="a2754-107">(Required)</span></span>  
  
-   <span data-ttu-id="a2754-108">El conjunto de entidades para el tipo de entidad implicado en el conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="a2754-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="a2754-109">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="a2754-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2754-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2754-110">Example</span></span>  
 <span data-ttu-id="a2754-111">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `WrittenBy` y `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="a2754-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 <span data-ttu-id="a2754-112">![Ejemplo de modelo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="a2754-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="a2754-113">El diagrama siguiente muestra un conjunto de asociaciones (`PublishedBy` y dos conjuntos de entidades (`Books` y `Publishers`) basados en el modelo conceptual mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a2754-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="a2754-114">Los extremos del conjunto de asociaciones son los conjuntos de entidades `Books` y `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="a2754-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="a2754-115">BI en el `Books` conjunto de entidades representa una instancia de la `Book` tipo de entidad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a2754-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="a2754-116">De forma similar, Pj representa un `Publisher` de instancia de la `Publishers` conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="a2754-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="a2754-117">BiPj representa una instancia de la `PublishedBy` asociación en el `PublishedBy` conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="a2754-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="a2754-118">![Establece en el ejemplo se](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="a2754-118">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="a2754-119">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un DSL denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="a2754-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="a2754-120">El siguiente CSDL define un contenedor de entidad con un conjunto de asociaciones para cada asociación en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="a2754-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="a2754-121">Observe que los extremos del conjunto de asociaciones se definen como parte de cada definición del conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="a2754-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="a2754-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2754-122">See Also</span></span>  
 [<span data-ttu-id="a2754-123">Conceptos básicos de modelo de datos de entidad</span><span class="sxs-lookup"><span data-stu-id="a2754-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="a2754-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="a2754-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
