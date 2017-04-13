---
title: "tipo de entidad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# tipo de entidad
El *tipo de entidad* es la unidad de creación fundamental para describir la estructura de datos con Entity Data Model \(EDM\).  En un modelo conceptual, un tipo de entidad representa la estructura de conceptos de nivel superior, como clientes o pedidos.  Un tipo de entidad es una plantilla para las instancias de tipo de entidad.  Cada plantilla contiene la información siguiente:  
  
-   Un nombre único.  \(Requerido\)  
  
-   Una [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) definida por una o más propiedades.  \(Requerido\)  
  
-   Datos en el formulario de [propiedades](../../../../docs/framework/data/adonet/property.md).  \(Opcional\)  
  
-   Las [propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) que permiten la navegación desde un [extremo](../../../../docs/framework/data/adonet/association-end.md) de una [asociación](../../../../docs/framework/data/adonet/association-type.md) al otro extremo.  \(Opcional\)  
  
 En una aplicación, una instancia de un tipo de entidad representa un objeto específico \(como un cliente o un pedido concreto\).  Cada instancia de un tipo de entidad debe tener una [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) única dentro de un [conjunto de entidades](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Dos instancias de tipo de entidad se consideran iguales solo si son del mismo tipo y los valores de sus claves de entidad son idénticos.  
  
## Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidad: `Book`, `Publisher` y `Author`:  
  
 ![Modelo de ejemplo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Tenga en cuenta que las propiedades de cada tipo de entidad que constituyen su clave de entidad se denotan con "\(Key\)".  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio \(DSL\) denominado lenguaje de definición de esquemas conceptuales \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\) para definir los modelos conceptuales.  El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [faceta](../../../../docs/framework/data/adonet/facet.md)