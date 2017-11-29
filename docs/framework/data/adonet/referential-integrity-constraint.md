---
title: "restricción de integridad referencial"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 10e469838073b4cf1faba1704b88b47f30b8b3d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="36823-102">restricción de integridad referencial</span><span class="sxs-lookup"><span data-stu-id="36823-102">referential integrity constraint</span></span>
<span data-ttu-id="36823-103">A *restricción de integridad referencial* en Entity Data Model (EDM) es similar a una restricción de integridad referencial en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="36823-103">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="36823-104">En la misma manera que una columna (o columnas) de una tabla de base de datos pueden hacer referencia a la clave principal de otra tabla, un [propiedad](../../../../docs/framework/data/adonet/property.md) (o propiedades) de un [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) pueden hacer referencia a la [clave de entidad ](../../../../docs/framework/data/adonet/entity-key.md) de otro tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="36823-104">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](../../../../docs/framework/data/adonet/property.md) (or properties) of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) can reference the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span> <span data-ttu-id="36823-105">El tipo de entidad que se hace referencia se denomina la *extremo principal* de la restricción.</span><span class="sxs-lookup"><span data-stu-id="36823-105">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="36823-106">El tipo de entidad que hace referencia el extremo principal se denomina la *extremo dependiente* de la restricción.</span><span class="sxs-lookup"><span data-stu-id="36823-106">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="36823-107">Una restricción de integridad referencial se define como parte de un [asociación](../../../../docs/framework/data/adonet/association-type.md) entre dos tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="36823-107">A referential integrity constraint is defined as part of an [association](../../../../docs/framework/data/adonet/association-type.md) between two entity types.</span></span> <span data-ttu-id="36823-108">La definición para una restricción de integridad referencial especifica la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="36823-108">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
-   <span data-ttu-id="36823-109">El extremo principal de la restricción.</span><span class="sxs-lookup"><span data-stu-id="36823-109">The principal end of the constraint.</span></span> <span data-ttu-id="36823-110">Es un tipo de entidad a cuya clave de entidad hace referencia el extremo dependiente.</span><span class="sxs-lookup"><span data-stu-id="36823-110">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
-   <span data-ttu-id="36823-111">La clave de entidad del extremo principal.</span><span class="sxs-lookup"><span data-stu-id="36823-111">The entity key of the principal end.</span></span>  
  
-   <span data-ttu-id="36823-112">El extremo dependiente de la restricción.</span><span class="sxs-lookup"><span data-stu-id="36823-112">The dependent end of the constraint.</span></span> <span data-ttu-id="36823-113">Es un tipo de entidad que tiene una o varias propiedades que hacen referencia a la clave de entidad del extremo principal.</span><span class="sxs-lookup"><span data-stu-id="36823-113">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
-   <span data-ttu-id="36823-114">La propiedad o propiedades que hacen la referencia del extremo dependiente.</span><span class="sxs-lookup"><span data-stu-id="36823-114">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="36823-115">El propósito de las restricciones de integridad referencial de EDM es garantizar la existencia de asociaciones válidas.</span><span class="sxs-lookup"><span data-stu-id="36823-115">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="36823-116">Para obtener más información, consulte [propiedad de clave externa](../../../../docs/framework/data/adonet/foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="36823-116">For more information, see [foreign key property](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="36823-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36823-117">Example</span></span>  
 <span data-ttu-id="36823-118">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `WrittenBy` y `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="36823-118">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="36823-119">El tipo de entidad `Book` tiene una propiedad, `PublisherId`, que hace referencia a la clave de entidad del tipo de entidad `Publisher` cuando se define una restricción de integridad referencial en la asociación `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="36823-119">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="36823-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span><span class="sxs-lookup"><span data-stu-id="36823-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span></span>  
  
 <span data-ttu-id="36823-121">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="36823-121">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="36823-122">El código CSDL siguiente define una restricción de integridad referencial en la asociación `PublishedBy` mostrada en el modelo conceptual anteriormente citado.</span><span class="sxs-lookup"><span data-stu-id="36823-122">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="36823-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="36823-123">See Also</span></span>  
 [<span data-ttu-id="36823-124">Conceptos básicos de modelo de datos de entidad</span><span class="sxs-lookup"><span data-stu-id="36823-124">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="36823-125">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="36823-125">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
