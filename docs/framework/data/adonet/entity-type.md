---
title: tipo de entidad
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3955de1873d80e85df713a557750e34e76efeb41
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502889"
---
# <a name="entity-type"></a>tipo de entidad
El *tipo de entidad* es el bloque de creación fundamental para describir la estructura de datos con Entity Data Model (EDM). En un modelo conceptual, un tipo de entidad representa la estructura de conceptos de nivel superior, como clientes o pedidos. Un tipo de entidad es una plantilla para las instancias de tipo de entidad. Cada plantilla contiene la información siguiente:  
  
-   Un nombre único. (Requerido)  
  
-   Un [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) definido por una o varias propiedades. (Requerido)  
  
-   Datos en forma de [propiedades](../../../../docs/framework/data/adonet/property.md). (Opcional)  
  
-   [Las propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) que permiten la navegación de una [final](../../../../docs/framework/data/adonet/association-end.md) de un [asociación](../../../../docs/framework/data/adonet/association-type.md) al otro extremo. (Opcional)  
  
 En una aplicación, una instancia de un tipo de entidad representa un objeto específico (como un cliente o un pedido concreto). Cada instancia de un tipo de entidad debe tener un único [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) dentro de un [conjunto de entidades](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Dos instancias de tipo de entidad se consideran iguales solo si son del mismo tipo y los valores de sus claves de entidad son idénticos.  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidad: `Book`, `Publisher` y `Author`:  
  
 ![Ejemplo de modelo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Tenga en cuenta que las propiedades de cada tipo de entidad que constituyen su clave de entidad se denotan con "(Key)".  
  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Vea también
- [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
- [facet](../../../../docs/framework/data/adonet/facet.md)
