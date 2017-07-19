---
title: "multiplicidad de extremo de asociaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# multiplicidad de extremo de asociaci&#243;n
La *multiplicidad de extremo de asociación* define el número de instancias de [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) que puede haber en un extremo de una [asociación](../../../../docs/framework/data/adonet/association-type.md).  
  
 Una multiplicidad de extremo de asociación puede tener uno de los valores siguientes:  
  
-   uno \(1\): indica que existe exactamente una instancia de tipo de entidad en el extremo de la asociación.  
  
-   cero o uno \(0..1\): indica que pueden existir cero o una instancia de tipo de entidad en el extremo de la asociación.  
  
-   varios \(\*\): indica que pueden existir cero, una o varias instancias de tipo de entidad en el extremo de la asociación.  
  
 Normalmente, una asociación se caracteriza por sus multiplicidades de extremo de asociación.  Por ejemplo, si los extremos de una asociación tienen multiplicidades uno \(1\) y varios \(\*\), la asociación se denomina una asociación uno a varios.  En el ejemplo siguiente, la asociación `PublishedBy` es una asociación uno a varios \(un publicador publica muchos libros y un libro solo puede ser publicado por un publicador\).  La asociación `WrittenBy` es una asociación varios a varios \(un libro puede tener varios autores y un autor puede escribir varios libros\).  
  
## Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`.  Los extremos de asociación para la asociación `PublishedBy` son los tipos de entidad `Book` y `Publisher`.  La multiplicidad del extremo `Publisher` es uno \(1\) y la multiplicidad del extremo `Book` es muchos \(\*\).  
  
 ![Modelo de ejemplo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 ADO.NET Entity Framework usa un lenguaje específico de dominio \(DSL\) denominado lenguaje de definición de esquemas conceptuales \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\) para definir los modelos conceptuales.  El código CSDL siguiente define la asociación `PublishedBy` mostrada en el diagrama anterior:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)