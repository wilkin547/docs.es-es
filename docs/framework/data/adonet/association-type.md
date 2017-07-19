---
title: "tipo de asociaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# tipo de asociaci&#243;n
El *tipo de asociación* \(también denominado asociación\) es el principal bloque de creación para la descripción de relaciones en Entity Data Model \(EDM\).  En un modelo conceptual, una asociación representa una relación entre dos [tipos de entidad](../../../../docs/framework/data/adonet/entity-type.md) \(como por ejemplo `Customer` y `Order`\).  En una aplicación, una instancia de una asociación representa una asociación concreta \(como por ejemplo una asociación entre una instancia de `Customer` y una instancia de `Order`\).  Las instancias de la asociación se agrupan de manera lógica en un [conjunto de asociaciones](../../../../docs/framework/data/adonet/association-set.md).  
  
 Una definición de asociación contiene la siguiente información:  
  
-   Un nombre único.  \(Necesario\)  
  
-   Dos [extremos de asociación](../../../../docs/framework/data/adonet/association-end.md), uno para cada tipo de entidad de la relación.  \(Necesario\)  
  
    > [!NOTE]
    >  Una asociación no puede representar una relación entre más de dos tipos de entidad.  Sin embargo, una asociación sí puede definir una auto\-relación especificando el mismo tipo de entidad para cada uno de sus extremos de asociación.  
  
-   Una [restricción de integridad referencial](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).  \(Opcional\)  
  
 Cada extremo de la asociación debe especificar una [multiplicidad de extremo de asociación](../../../../docs/framework/data/adonet/association-end-multiplicity.md) que indica el número de instancias de tipo de entidad que pueden existir en un extremo de la asociación.  La multiplicidad de extremo de asociación puede tener el valor uno \(1\), cero o uno \(0..1\), o muchos \(\*\).  Es posible obtener acceso a las instancias de tipo de entidad situadas en un extremo de la asociación a través de las [propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) o las claves externas si estas se exponen en un tipo de entidad.  Para obtener más información, vea [Entity Data Model: Claves externas](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`.  Los extremos de asociación para la asociación `PublishedBy` son los tipos de entidad `Book` y `Publisher`.  La multiplicidad del extremo `Publisher` es uno \(1\) y la multiplicidad del extremo `Book` es muchos \(\*\), lo que indica que un editor publica muchos libros y que un libro solo puede ser publicado por un editor.  
  
 ![Modelo de ejemplo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio \(DSL\) denominado lenguaje de definición de esquemas conceptuales \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\) para definir los modelos conceptuales.  El código CSDL siguiente define la asociación `PublishedBy` mostrada en el diagrama anterior:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)