---
title: propiedad de clave externa
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 044be77cbbd8b5ad16cfbd5bbf1fdde984a060d5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="foreign-key-property"></a><span data-ttu-id="4eb60-102">propiedad de clave externa</span><span class="sxs-lookup"><span data-stu-id="4eb60-102">foreign key property</span></span>
<span data-ttu-id="4eb60-103">A *propiedad de clave externa* en Entity Data Model (EDM) es un tipo primitivo [propiedad](../../../../docs/framework/data/adonet/property.md) (o un conjunto de propiedades de tipo primitivo) en un [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) que contiene el [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) de otro tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="4eb60-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](../../../../docs/framework/data/adonet/property.md) (or a set of primitive type properties) on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that contains the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="4eb60-104">Una propiedad de clave externa es análoga a una columna de clave externa de una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="4eb60-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="4eb60-105">En la misma manera que se usan columnas de clave externa en una base de datos relacional para crear relaciones entre filas de tablas, las propiedades de clave externa en un modelo conceptual se usan para establecer [asociaciones](../../../../docs/framework/data/adonet/association-type.md) entre tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="4eb60-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](../../../../docs/framework/data/adonet/association-type.md) between entity types.</span></span> <span data-ttu-id="4eb60-106">A [restricción de integridad referencial](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) se utiliza para definir una asociación entre dos tipos de entidad cuando uno de ellos tiene una propiedad de clave externa.</span><span class="sxs-lookup"><span data-stu-id="4eb60-106">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4eb60-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4eb60-107">Example</span></span>  
 <span data-ttu-id="4eb60-108">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="4eb60-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="4eb60-109">El tipo de entidad `Book` tiene una propiedad, `PublisherId`, que hace referencia a la clave de entidad del tipo de entidad `Publisher` cuando se define una restricción de integridad referencial en la asociación `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="4eb60-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="4eb60-110">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span><span class="sxs-lookup"><span data-stu-id="4eb60-110">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span></span>  
  
 <span data-ttu-id="4eb60-111">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="4eb60-111">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="4eb60-112">El código CSDL siguiente usa la propiedad de clave externa `PublisherId` para definir una restricción de integridad referencial en la asociación `PublishedBy` incluida en el modelo conceptual mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4eb60-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="4eb60-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4eb60-113">See Also</span></span>  
 [<span data-ttu-id="4eb60-114">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="4eb60-114">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="4eb60-115">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="4eb60-115">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
