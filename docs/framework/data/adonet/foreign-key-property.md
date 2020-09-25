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
# <a name="foreign-key-property"></a>propiedad de clave externa

Una *propiedad de clave externa* en el Entity Data Model (EDM) es una [propiedad](property.md) de tipo primitivo (o un conjunto de propiedades de tipo primitivo) en un [tipo de entidad](entity-type.md) que contiene la clave de [entidad](entity-key.md) de otro tipo de entidad.  
  
 Una propiedad de clave externa es análoga a una columna de clave externa de una base de datos relacional. Del mismo modo que las columnas de clave externa se utilizan en una base de datos relacional para crear relaciones entre las filas de las tablas, las propiedades de clave externa en un modelo conceptual se utilizan para establecer [asociaciones](association-type.md) entre tipos de entidad. Una [restricción de integridad referencial](referential-integrity-constraint.md) se utiliza para definir una asociación entre dos tipos de entidad cuando uno de los tipos tiene una propiedad de clave externa.  
  
## <a name="example"></a>Ejemplo  

 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`. El tipo de entidad `Book` tiene una propiedad, `PublisherId`, que hace referencia a la clave de entidad del tipo de entidad `Publisher` cuando se define una restricción de integridad referencial en la asociación `PublishedBy`.  
  
 ![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Ejemplo de un modelo de restricción referencial")  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El código CSDL siguiente usa la propiedad de clave externa `PublisherId` para definir una restricción de integridad referencial en la asociación `PublishedBy` incluida en el modelo conceptual mostrado anteriormente.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Consulte también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
