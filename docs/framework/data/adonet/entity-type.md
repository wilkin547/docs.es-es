---
title: tipo de entidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9b32f188d09114cdef4327df3aa1a74a304e7c3e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="entity-type"></a>tipo de entidad
El *tipo de entidad* es el bloque de creación fundamental para describir la estructura de datos con Entity Data Model (EDM). En un modelo conceptual, un tipo de entidad representa la estructura de conceptos de nivel superior, como clientes o pedidos. Un tipo de entidad es una plantilla para las instancias de tipo de entidad. Cada plantilla contiene la información siguiente:  
  
-   Un nombre único. (Requerido)  
  
-   Un [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) definido por una o varias propiedades. (Requerido)  
  
-   Datos en forma de [propiedades](../../../../docs/framework/data/adonet/property.md). (Opcional)  
  
-   [Propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) que permiten la navegación desde un [final](../../../../docs/framework/data/adonet/association-end.md) de un [asociación](../../../../docs/framework/data/adonet/association-type.md) hacia el otro extremo. (Opcional)  
  
 En una aplicación, una instancia de un tipo de entidad representa un objeto específico (como un cliente o un pedido concreto). Cada instancia de un tipo de entidad debe tener un único [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) dentro de un [conjunto de entidades](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Dos instancias de tipo de entidad se consideran iguales solo si son del mismo tipo y los valores de sus claves de entidad son idénticos.  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidad: `Book`, `Publisher` y `Author`:  
  
 ![Ejemplo de modelo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Tenga en cuenta que las propiedades de cada tipo de entidad que constituyen su clave de entidad se denotan con "(Key)".  
  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [facet](../../../../docs/framework/data/adonet/facet.md)
