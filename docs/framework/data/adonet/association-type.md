---
title: tipo de asociación
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 17465dbec3f5e2896cf755a1f8585734388f54ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948299"
---
# <a name="association-type"></a>tipo de asociación
Un *tipo de asociación* (también denominado Asociación) es el bloque de creación fundamental para describir las relaciones en el Entity Data Model (EDM). En un modelo conceptual, una asociación representa una relación entre dos [tipos de entidad](../../../../docs/framework/data/adonet/entity-type.md) ( `Customer` como y `Order`). En una aplicación, una instancia de una asociación representa una asociación concreta (como por ejemplo una asociación entre una instancia de `Customer` y una instancia de `Order`). Las instancias de asociación se agrupan lógicamente en un [conjunto de asociaciones](../../../../docs/framework/data/adonet/association-set.md).  
  
 Una definición de asociación contiene la siguiente información:  
  
- Un nombre único. (Necesario)  
  
- Dos [extremos](../../../../docs/framework/data/adonet/association-end.md)de la asociación, uno para cada tipo de entidad de la relación. (Necesario)  
  
    > [!NOTE]
    > Una asociación no puede representar una relación entre más de dos tipos de entidad. Sin embargo, una asociación sí puede definir una auto-relación especificando el mismo tipo de entidad para cada uno de sus extremos de asociación.  
  
- [Restricción de integridad referencial](../../../../docs/framework/data/adonet/referential-integrity-constraint.md). (Opcional)  
  
 Cada extremo de la asociación debe especificar una [multiplicidad de extremo de asociación](../../../../docs/framework/data/adonet/association-end-multiplicity.md) que indica el número de instancias de tipo de entidad que pueden estar en un extremo de la asociación. Una multiplicidad de extremo de asociación puede tener un valor de uno (1), cero o uno (0.. 1) o varios (\*). Se puede tener acceso a las instancias de tipo de entidad en un extremo de una asociación a través de [las propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) o las claves externas si se exponen en un tipo de entidad. Para obtener más información, [vea Entity Data Model: Claves](../../../../docs/framework/data/adonet/foreign-key-property.md)externas.  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`. Los extremos de asociación para la asociación `PublishedBy` son los tipos de entidad `Book` y `Publisher`. La multiplicidad del `Publisher` extremo es uno (1) y la multiplicidad `Book` del extremo es muchos (\*), lo que indica que un publicador publica muchos libros y un libro publicado por un publicador.  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-type/example-model-three-entity-types.gif)  
  
 El [Entity Framework ADO.net](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El código CSDL siguiente define la asociación `PublishedBy` mostrada en el diagrama anterior:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
