---
title: "propiedad de clave externa | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# propiedad de clave externa
Una *propiedad de clave externa* en Entity Data Model \(EDM\) es una [propiedad](../../../../docs/framework/data/adonet/property.md) de tipo primitivo \(o un conjunto de propiedades de tipo primitivo\) en un [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) que contiene la [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) de otro tipo de entidad.  
  
 Una propiedad de clave externa es análoga a una columna de clave externa de una base de datos relacional.  Del mismo modo que en una base de datos relacional se usan las columnas de clave externa para crear relaciones entre las filas de las tablas, en un modelo conceptual se usan las propiedades de clave externa para establecer [asociaciones](../../../../docs/framework/data/adonet/association-type.md) entre tipos de entidad.  Para definir una asociación entre dos tipos de entidad cuando uno de ellos tiene una propiedad de clave externa se emplea una [restricción de integridad referencial](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).  
  
## Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.  El tipo de entidad `Book` tiene una propiedad, `PublisherId`, que hace referencia a la clave de entidad del tipo de entidad `Publisher` cuando se define una restricción de integridad referencial en la asociación `PublishedBy`.  
  
 ![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio \(DSL\) denominado lenguaje de definición de esquemas conceptuales \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\) para definir los modelos conceptuales.  El código CSDL siguiente usa la propiedad de clave externa `PublisherId` para definir una restricción de integridad referencial en la asociación `PublishedBy` incluida en el modelo conceptual mostrado anteriormente.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)