---
title: conjunto de asociaciones
ms.date: 03/30/2017
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
ms.openlocfilehash: 58d8794a21cc37ab84386c820b192fb29946095c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153435"
---
# <a name="association-set"></a><span data-ttu-id="030bf-102">conjunto de asociaciones</span><span class="sxs-lookup"><span data-stu-id="030bf-102">association set</span></span>

<span data-ttu-id="030bf-103">Un *conjunto de asociaciones* es un contenedor lógico para las instancias de [Asociación](association-type.md) del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="030bf-103">An *association set* is a logical container for [association](association-type.md) instances of the same type.</span></span> <span data-ttu-id="030bf-104">Un conjunto de asociaciones no es una construcción del modelado de datos; es decir, no describe la estructura de datos o relaciones.</span><span class="sxs-lookup"><span data-stu-id="030bf-104">An association set is not a data modeling construct; that is, it does not describe the structure of data or relationships.</span></span> <span data-ttu-id="030bf-105">En su lugar, un conjunto de asociaciones proporciona una construcción para que un entorno de hospedaje o de almacenamiento (como Common Language Runtime o una base de datos de SQL Server) agrupe las instancias de asociaciones a fin de que se puedan asignar a un almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="030bf-105">Instead, an association set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group association instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="030bf-106">Un conjunto de asociaciones se define dentro de un [contenedor de entidades](entity-container.md), que es una agrupación lógica de [conjuntos de entidades](entity-set.md) y conjuntos de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="030bf-106">An association set is defined within an [entity container](entity-container.md), which is a logical grouping of [entity sets](entity-set.md) and association sets.</span></span>  
  
 <span data-ttu-id="030bf-107">Una definición de un conjunto de asociaciones contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="030bf-107">A definition for an association set contains the following information:</span></span>  
  
- <span data-ttu-id="030bf-108">El nombre del conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="030bf-108">The association set name.</span></span> <span data-ttu-id="030bf-109">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="030bf-109">(Required)</span></span>  
  
- <span data-ttu-id="030bf-110">La asociación cuyas instancias contendrá.</span><span class="sxs-lookup"><span data-stu-id="030bf-110">The association of which it will contain instances.</span></span> <span data-ttu-id="030bf-111">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="030bf-111">(Required)</span></span>  
  
- <span data-ttu-id="030bf-112">Dos [extremos del conjunto de asociaciones](association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="030bf-112">Two [association set ends](association-set-end.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="030bf-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="030bf-113">Example</span></span>  

 <span data-ttu-id="030bf-114">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="030bf-114">The diagram below shows a conceptual model with two associations: `PublishedBy`, and `WrittenBy`.</span></span> <span data-ttu-id="030bf-115">Aunque la información sobre los conjuntos de asociaciones no se muestra en el diagrama, el diagrama siguiente muestra un ejemplo de conjuntos de asociaciones y conjuntos de entidades basados en este modelo.</span><span class="sxs-lookup"><span data-stu-id="030bf-115">Although information about association sets is not conveyed in the diagram, the next diagram shows an example of association sets and entity sets based on this model.</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-set/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="030bf-117">El siguiente ejemplo muestra un conjunto de asociaciones (`PublishedBy` y dos conjuntos de entidades (`Books` y `Publishers`) basados en el modelo conceptual mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="030bf-117">The following example shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="030bf-118">BI en el `Books` conjunto de entidades representa una instancia del `Book` tipo de entidad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="030bf-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="030bf-119">De forma similar, PJ representa una `Publisher` instancia en el `Publishers` conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="030bf-119">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="030bf-120">BiPj representa una instancia de la `PublishedBy` asociación en el `PublishedBy` conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="030bf-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Captura de pantalla que muestra un ejemplo de conjuntos.](./media/association-set/sets-example-association.gif)  
  
 <span data-ttu-id="030bf-122">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="030bf-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="030bf-123">El siguiente CSDL define un contenedor de entidad con un conjunto de asociaciones para cada asociación en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="030bf-123">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="030bf-124">Observe que el nombre y asociación para cada conjunto de asociaciones se definen utilizando los atributos XML.</span><span class="sxs-lookup"><span data-stu-id="030bf-124">Note that the name and association for each association set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="030bf-125">Es posible definir varios conjuntos de asociaciones por asociación, siempre y cuando no haya dos conjuntos de asociaciones que compartan un [extremo del conjunto de asociaciones](association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="030bf-125">It is possible to define multiple association sets per association, as long as no two association sets share an [association set end](association-set-end.md).</span></span> <span data-ttu-id="030bf-126">En el siguiente CSDL se define un contenedor de entidades con dos conjuntos de asociaciones para la asociación `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="030bf-126">The following CSDL defines an entity container with two association sets for the `WrittenBy` association.</span></span> <span data-ttu-id="030bf-127">Observe que se han definido varios conjuntos de entidades para los tipos de entidad `Book` y `Author` y que ningún conjunto de asociaciones comparte un extremo del conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="030bf-127">Notice that multiple entity sets have been defined for the `Book` and `Author` entity types and that no association set shares an association set end.</span></span>  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a><span data-ttu-id="030bf-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="030bf-128">See also</span></span>

- [<span data-ttu-id="030bf-129">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="030bf-129">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="030bf-130">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="030bf-130">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="030bf-131">propiedad de clave externa</span><span class="sxs-lookup"><span data-stu-id="030bf-131">foreign key property</span></span>](foreign-key-property.md)
