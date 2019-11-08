---
title: tipo de entidad
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 1dafce5f7f95ba6f391c8742944f40a9afa7dcf8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737808"
---
# <a name="entity-type"></a>tipo de entidad
El *tipo de entidad* es el bloque de creación fundamental para describir la estructura de los datos con el Entity Data Model (EDM). En un modelo conceptual, un tipo de entidad representa la estructura de conceptos de nivel superior, como clientes o pedidos. Un tipo de entidad es una plantilla para las instancias de tipo de entidad. Cada plantilla contiene la información siguiente:  
  
- Un nombre único. (Requerido)  
  
- Una [clave de entidad](entity-key.md) definida por una o más propiedades. (Requerido)  
  
- Datos en forma de [propiedades](property.md). (Opcional)  
  
- [Propiedades de navegación](navigation-property.md) que permiten la navegación desde un [extremo](association-end.md) de una [Asociación](association-type.md) al otro extremo. (Opcional)  
  
 En una aplicación, una instancia de un tipo de entidad representa un objeto específico (como un cliente o un pedido concreto). Cada instancia de un tipo de entidad debe tener una [clave de entidad](entity-key.md) única dentro de un [conjunto de entidades](entity-set.md).  
  
 Dos instancias de tipo de entidad se consideran iguales solo si son del mismo tipo y los valores de sus claves de entidad son idénticos.  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidad: `Book`, `Publisher` y `Author`:  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/entity-type/example-model-three-entity-types.gif)  
  
 Tenga en cuenta que las propiedades de cada tipo de entidad que constituyen su clave de entidad se denotan con "(Key)".  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [facet](facet.md)
