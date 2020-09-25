---
title: propiedad de clave externa
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: be0fcb94b0b457a33c17e7125cd22db50f298cc6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189323"
---
# <a name="foreign-key-property"></a><span data-ttu-id="7f934-102">propiedad de clave externa</span><span class="sxs-lookup"><span data-stu-id="7f934-102">foreign key property</span></span>

<span data-ttu-id="7f934-103">Una *propiedad de clave externa* en el Entity Data Model (EDM) es una [propiedad](property.md) de tipo primitivo (o un conjunto de propiedades de tipo primitivo) en un [tipo de entidad](entity-type.md) que contiene la clave de [entidad](entity-key.md) de otro tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="7f934-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](property.md) (or a set of primitive type properties) on an [entity type](entity-type.md) that contains the [entity key](entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="7f934-104">Una propiedad de clave externa es análoga a una columna de clave externa de una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="7f934-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="7f934-105">Del mismo modo que las columnas de clave externa se utilizan en una base de datos relacional para crear relaciones entre las filas de las tablas, las propiedades de clave externa en un modelo conceptual se utilizan para establecer [asociaciones](association-type.md) entre tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="7f934-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](association-type.md) between entity types.</span></span> <span data-ttu-id="7f934-106">Una [restricción de integridad referencial](referential-integrity-constraint.md) se utiliza para definir una asociación entre dos tipos de entidad cuando uno de los tipos tiene una propiedad de clave externa.</span><span class="sxs-lookup"><span data-stu-id="7f934-106">A [referential integrity constraint](referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f934-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f934-107">Example</span></span>  

 <span data-ttu-id="7f934-108">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="7f934-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="7f934-109">El tipo de entidad `Book` tiene una propiedad, `PublisherId`, que hace referencia a la clave de entidad del tipo de entidad `Publisher` cuando se define una restricción de integridad referencial en la asociación `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="7f934-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="7f934-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Ejemplo de un modelo de restricción referencial")</span><span class="sxs-lookup"><span data-stu-id="7f934-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="7f934-111">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="7f934-111">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="7f934-112">El código CSDL siguiente usa la propiedad de clave externa `PublisherId` para definir una restricción de integridad referencial en la asociación `PublishedBy` incluida en el modelo conceptual mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7f934-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="7f934-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f934-113">See also</span></span>

- [<span data-ttu-id="7f934-114">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7f934-114">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="7f934-115">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7f934-115">Entity Data Model</span></span>](entity-data-model.md)
