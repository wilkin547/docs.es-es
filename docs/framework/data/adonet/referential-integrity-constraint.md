---
title: restricción de integridad referencial
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: 28880c7085f8b4e3dd2e51b5633c1f0e2a984a4b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794444"
---
# <a name="referential-integrity-constraint"></a>restricción de integridad referencial
Una *restricción de integridad referencial* en el Entity Data Model (EDM) es similar a una restricción de integridad referencial en una base de datos relacional. Del mismo modo que una columna (o columnas) de una tabla de base de datos puede hacer referencia a la clave principal de otra tabla, una [propiedad](property.md) (o propiedades) de un [tipo de entidad](entity-type.md) puede hacer referencia a la [clave de entidad](entity-key.md) de otro tipo de entidad. El tipo de entidad al que se hace referencia se denomina *extremo principal* de la restricción. El tipo de entidad que hace referencia al extremo principal se denomina *extremo dependiente* de la restricción.  
  
 Una restricción de integridad referencial se define como parte de una [Asociación](association-type.md) entre dos tipos de entidad. La definición para una restricción de integridad referencial especifica la siguiente información:  
  
- El extremo principal de la restricción. Es un tipo de entidad a cuya clave de entidad hace referencia el extremo dependiente.  
  
- La clave de entidad del extremo principal.  
  
- El extremo dependiente de la restricción. Es un tipo de entidad que tiene una o varias propiedades que hacen referencia a la clave de entidad del extremo principal.  
  
- La propiedad o propiedades que hacen la referencia del extremo dependiente.  
  
 El propósito de las restricciones de integridad referencial de EDM es garantizar la existencia de asociaciones válidas. Para obtener más información, consulte [Foreign Key Property](foreign-key-property.md).  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `WrittenBy` y `PublishedBy`. El tipo de entidad `Book` tiene una propiedad, `PublisherId`, que hace referencia a la clave de entidad del tipo de entidad `Publisher` cuando se define una restricción de integridad referencial en la asociación `PublishedBy`.  
  
 ![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Ejemplo de un modelo de restricción referencial")  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](./ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El código CSDL siguiente define una restricción de integridad referencial en la asociación `PublishedBy` mostrada en el modelo conceptual anteriormente citado.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
