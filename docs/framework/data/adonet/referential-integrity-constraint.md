---
title: restricción de integridad referencial
description: Obtenga información sobre las restricciones de integridad referencial en el Entity Data Model, que garantizan que las asociaciones válidas siempre existan entre los tipos de entidad.
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: 6ade9d0155a6915757c7f47c5cb3ab0a51dbd437
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172741"
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="7a372-103">restricción de integridad referencial</span><span class="sxs-lookup"><span data-stu-id="7a372-103">referential integrity constraint</span></span>

<span data-ttu-id="7a372-104">Una *restricción de integridad referencial* en el Entity Data Model (EDM) es similar a una restricción de integridad referencial en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="7a372-104">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="7a372-105">Del mismo modo que una columna (o columnas) de una tabla de base de datos puede hacer referencia a la clave principal de otra tabla, una [propiedad](property.md) (o propiedades) de un [tipo de entidad](entity-type.md) puede hacer referencia a la [clave de entidad](entity-key.md) de otro tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="7a372-105">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](property.md) (or properties) of an [entity type](entity-type.md) can reference the [entity key](entity-key.md) of another entity type.</span></span> <span data-ttu-id="7a372-106">El tipo de entidad al que se hace referencia se denomina *extremo principal* de la restricción.</span><span class="sxs-lookup"><span data-stu-id="7a372-106">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="7a372-107">El tipo de entidad que hace referencia al extremo principal se denomina *extremo dependiente* de la restricción.</span><span class="sxs-lookup"><span data-stu-id="7a372-107">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="7a372-108">Una restricción de integridad referencial se define como parte de una [Asociación](association-type.md) entre dos tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="7a372-108">A referential integrity constraint is defined as part of an [association](association-type.md) between two entity types.</span></span> <span data-ttu-id="7a372-109">La definición para una restricción de integridad referencial especifica la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7a372-109">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
- <span data-ttu-id="7a372-110">El extremo principal de la restricción.</span><span class="sxs-lookup"><span data-stu-id="7a372-110">The principal end of the constraint.</span></span> <span data-ttu-id="7a372-111">Es un tipo de entidad a cuya clave de entidad hace referencia el extremo dependiente.</span><span class="sxs-lookup"><span data-stu-id="7a372-111">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
- <span data-ttu-id="7a372-112">La clave de entidad del extremo principal.</span><span class="sxs-lookup"><span data-stu-id="7a372-112">The entity key of the principal end.</span></span>  
  
- <span data-ttu-id="7a372-113">El extremo dependiente de la restricción.</span><span class="sxs-lookup"><span data-stu-id="7a372-113">The dependent end of the constraint.</span></span> <span data-ttu-id="7a372-114">Es un tipo de entidad que tiene una o varias propiedades que hacen referencia a la clave de entidad del extremo principal.</span><span class="sxs-lookup"><span data-stu-id="7a372-114">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
- <span data-ttu-id="7a372-115">La propiedad o propiedades que hacen la referencia del extremo dependiente.</span><span class="sxs-lookup"><span data-stu-id="7a372-115">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="7a372-116">El propósito de las restricciones de integridad referencial de EDM es garantizar la existencia de asociaciones válidas.</span><span class="sxs-lookup"><span data-stu-id="7a372-116">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="7a372-117">Para obtener más información, consulte [Foreign Key Property](foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="7a372-117">For more information, see [foreign key property](foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a372-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a372-118">Example</span></span>  

 <span data-ttu-id="7a372-119">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `WrittenBy` y `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="7a372-119">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="7a372-120">El tipo de entidad `Book` tiene una propiedad, `PublisherId`, que hace referencia a la clave de entidad del tipo de entidad `Publisher` cuando se define una restricción de integridad referencial en la asociación `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="7a372-120">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="7a372-121">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Ejemplo de un modelo de restricción referencial")</span><span class="sxs-lookup"><span data-stu-id="7a372-121">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="7a372-122">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="7a372-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="7a372-123">El código CSDL siguiente define una restricción de integridad referencial en la asociación `PublishedBy` mostrada en el modelo conceptual anteriormente citado.</span><span class="sxs-lookup"><span data-stu-id="7a372-123">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="7a372-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a372-124">See also</span></span>

- [<span data-ttu-id="7a372-125">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7a372-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="7a372-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7a372-126">Entity Data Model</span></span>](entity-data-model.md)
