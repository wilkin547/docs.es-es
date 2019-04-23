---
title: propiedad de clave externa
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: 74117b30ca54f7c57bd970003fc6f5dcc54d553f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218022"
---
# <a name="foreign-key-property"></a>propiedad de clave externa
Un *propiedad de clave externa* en Entity Data Model (EDM) es un tipo primitivo [propiedad](../../../../docs/framework/data/adonet/property.md) (o un conjunto de propiedades de tipo primitivo) en un [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) que contiene el [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) de otro tipo de entidad.  
  
 Una propiedad de clave externa es análoga a una columna de clave externa de una base de datos relacional. En la misma manera que se usan columnas de clave externa en una base de datos relacional para crear relaciones entre las filas de tablas, las propiedades de clave externa en un modelo conceptual se usan para establecer [asociaciones](../../../../docs/framework/data/adonet/association-type.md) entre tipos de entidad. Un [restricción de integridad referencial](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) se utiliza para definir una asociación entre dos tipos de entidad cuando uno de los tipos tiene una propiedad de clave externa.  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`. El tipo de entidad `Book` tiene una propiedad, `PublisherId`, que hace referencia a la clave de entidad del tipo de entidad `Publisher` cuando se define una restricción de integridad referencial en la asociación `PublishedBy`.  
  
 ![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "ejemplo de un modelo de la restricción referencial")  
  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El código CSDL siguiente usa la propiedad de clave externa `PublisherId` para definir una restricción de integridad referencial en la asociación `PublishedBy` incluida en el modelo conceptual mostrado anteriormente.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
