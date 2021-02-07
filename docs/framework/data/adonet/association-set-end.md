---
description: 'Más información sobre: extremo del conjunto de asociaciones'
title: extremo del conjunto de asociaciones
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 12e01a3fb947f6fabd5e1a93ef475132418963df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697678"
---
# <a name="association-set-end"></a><span data-ttu-id="dd8a8-103">extremo del conjunto de asociaciones</span><span class="sxs-lookup"><span data-stu-id="dd8a8-103">association set end</span></span>

<span data-ttu-id="dd8a8-104">Un *extremo del conjunto de asociaciones* identifica el [tipo de entidad](entity-type.md) y el [conjunto de entidades](entity-set.md) al final de un [conjunto de asociaciones](association-set.md).</span><span class="sxs-lookup"><span data-stu-id="dd8a8-104">An *association set end* identifies the [entity type](entity-type.md) and the [entity set](entity-set.md) at the end of an [association set](association-set.md).</span></span> <span data-ttu-id="dd8a8-105">Los extremos de conjuntos de asociaciones se definen como parte de un conjunto de asociaciones, que debe tener exactamente dos extremos.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-105">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="dd8a8-106">Una definición de extremo de conjunto de asociaciones contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd8a8-106">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="dd8a8-107">Uno de los tipos de entidad implicados en el conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-107">One of the entity types involved in the association set.</span></span> <span data-ttu-id="dd8a8-108">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="dd8a8-108">(Required)</span></span>  
  
- <span data-ttu-id="dd8a8-109">El conjunto de entidades para el tipo de entidad implicado en el conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-109">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="dd8a8-110">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="dd8a8-110">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd8a8-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd8a8-111">Example</span></span>  

 <span data-ttu-id="dd8a8-112">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `WrittenBy` y `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-112">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="dd8a8-114">El diagrama siguiente muestra un conjunto de asociaciones (`PublishedBy` y dos conjuntos de entidades (`Books` y `Publishers`) basados en el modelo conceptual mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-114">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="dd8a8-115">Los extremos del conjunto de asociaciones son los conjuntos de entidades `Books` y `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-115">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="dd8a8-116">BI en el `Books` conjunto de entidades representa una instancia del `Book` tipo de entidad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-116">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="dd8a8-117">De forma similar, PJ representa una `Publisher` instancia en el `Publishers` conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-117">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="dd8a8-118">BiPj representa una instancia de la `PublishedBy` asociación en el `PublishedBy` conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-118">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Captura de pantalla que muestra un ejemplo de conjuntos.](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="dd8a8-120">El [Entity Framework ADO.net](./ef/index.md) usa un DSL denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-120">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="dd8a8-121">El siguiente CSDL define un contenedor de entidad con un conjunto de asociaciones para cada asociación en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-121">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="dd8a8-122">Observe que los extremos del conjunto de asociaciones se definen como parte de cada definición del conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="dd8a8-122">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="dd8a8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd8a8-123">See also</span></span>

- [<span data-ttu-id="dd8a8-124">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="dd8a8-124">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="dd8a8-125">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="dd8a8-125">Entity Data Model</span></span>](entity-data-model.md)
