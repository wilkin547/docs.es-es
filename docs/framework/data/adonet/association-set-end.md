---
title: extremo del conjunto de asociaciones
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 48ba84d46e380462405551cc2d826d84368b351a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786931"
---
# <a name="association-set-end"></a><span data-ttu-id="626d5-102">extremo del conjunto de asociaciones</span><span class="sxs-lookup"><span data-stu-id="626d5-102">association set end</span></span>
<span data-ttu-id="626d5-103">Un *extremo del conjunto de asociaciones* identifica el [tipo de entidad](entity-type.md) y el [conjunto de entidades](entity-set.md) al final de un [conjunto de asociaciones](association-set.md).</span><span class="sxs-lookup"><span data-stu-id="626d5-103">An *association set end* identifies the [entity type](entity-type.md) and the [entity set](entity-set.md) at the end of an [association set](association-set.md).</span></span> <span data-ttu-id="626d5-104">Los extremos de conjuntos de asociaciones se definen como parte de un conjunto de asociaciones, que debe tener exactamente dos extremos.</span><span class="sxs-lookup"><span data-stu-id="626d5-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="626d5-105">Una definición de extremo de conjunto de asociaciones contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="626d5-105">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="626d5-106">Uno de los tipos de entidad implicados en el conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="626d5-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="626d5-107">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="626d5-107">(Required)</span></span>  
  
- <span data-ttu-id="626d5-108">El conjunto de entidades para el tipo de entidad implicado en el conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="626d5-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="626d5-109">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="626d5-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="626d5-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="626d5-110">Example</span></span>  
 <span data-ttu-id="626d5-111">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `WrittenBy` y `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="626d5-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="626d5-113">El diagrama siguiente muestra un conjunto de asociaciones (`PublishedBy` y dos conjuntos de entidades (`Books` y `Publishers`) basados en el modelo conceptual mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="626d5-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="626d5-114">Los extremos del conjunto de asociaciones son los conjuntos de entidades `Books` y `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="626d5-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="626d5-115">BI en el `Books` conjunto de entidades representa una instancia `Book` del tipo de entidad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="626d5-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="626d5-116">De forma similar, PJ `Publisher` representa una instancia `Publishers` en el conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="626d5-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="626d5-117">BiPj representa una instancia de la `PublishedBy` asociación en el `PublishedBy` conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="626d5-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Captura de pantalla que muestra un ejemplo de conjuntos.](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="626d5-119">El [Entity Framework ADO.net](./ef/index.md) usa un DSL denominado lenguaje de definición de esquemas conceptuales ([CSDL](./ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="626d5-119">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="626d5-120">El siguiente CSDL define un contenedor de entidad con un conjunto de asociaciones para cada asociación en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="626d5-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="626d5-121">Observe que los extremos del conjunto de asociaciones se definen como parte de cada definición del conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="626d5-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="626d5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="626d5-122">See also</span></span>

- [<span data-ttu-id="626d5-123">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="626d5-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="626d5-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="626d5-124">Entity Data Model</span></span>](entity-data-model.md)
