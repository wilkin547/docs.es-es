---
title: "extremo del conjunto de asociaciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# extremo del conjunto de asociaciones
Un *extremo de conjunto de asociaciones* identifica el [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) y el [conjunto de entidades](../../../../docs/framework/data/adonet/entity-set.md) del extremo de un [conjunto de asociaciones](../../../../docs/framework/data/adonet/association-set.md).  Los extremos de conjuntos de asociaciones se definen como parte de un conjunto de asociaciones, que debe tener exactamente dos extremos.  
  
 Una definición de extremo de conjunto de asociaciones contiene la información siguiente:  
  
-   Uno de los tipos de entidad implicados en el conjunto de asociaciones.  \(Necesario\)  
  
-   El conjunto de entidades para el tipo de entidad implicado en el conjunto de asociaciones.  \(Necesario\)  
  
## Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `WrittenBy` y `PublishedBy`.  
  
 ![Modelo de ejemplo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 El diagrama siguiente muestra un conjunto de asociaciones \(`PublishedBy` y dos conjuntos de entidades \(`Books` y `Publishers`\) basados en el modelo conceptual mostrado anteriormente.  Los extremos del conjunto de asociaciones son los conjuntos de entidades `Publishers` y `Books`.  En el conjunto de entidades `Books`, Bi representa una instancia del tipo de entidad `Book` en tiempo de ejecución.  De igual forma, Pj representa una instancia de `Publisher` en el conjunto de entidades `Publishers`.  BiPj representa una instancia de la asociación `PublishedBy` en el conjunto de asociaciones `PublishedBy`.  
  
 ![Ejemplo de conjuntos](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un DSL denominado lenguaje de definición de esquemas conceptuales \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\) para definir los modelos conceptuales.  El siguiente CSDL define un contenedor de entidad con un conjunto de asociaciones para cada asociación en el diagrama anterior.  Observe que los extremos del conjunto de asociaciones se definen como parte de cada definición del conjunto de asociaciones.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)