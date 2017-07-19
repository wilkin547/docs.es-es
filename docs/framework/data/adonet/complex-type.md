---
title: "tipo complejo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# tipo complejo
Un *tipo complejo* es una plantilla para definir propiedades enriquecidas y estructuradas para los [tipos de entidad](../../../../docs/framework/data/adonet/entity-type.md) u otros tipos complejos.  Cada plantilla contiene lo siguiente:  
  
-   Un nombre único.  \(Necesario\)  
  
    > [!NOTE]
    >  El nombre de un tipo complejo no puede coincidir con el nombre de un tipo de entidad dentro del mismo espacio de nombres.  
  
-   Datos en forma de una o más [propiedades](../../../../docs/framework/data/adonet/property.md).  \(Opcional\)  
  
    > [!NOTE]
    >  Una propiedad de un tipo complejo puede ser otro tipo complejo.  
  
 Un tipo complejo es similar a un tipo de entidad, ya que un tipo complejo puede llevar una carga de datos en forma de propiedades de tipo primitivo u otros tipos complejos.  Sin embargo, existen algunas diferencias clave entre los tipos complejos y los tipos de entidad:  
  
-   Los tipos complejos no tienen identidades y, por consiguiente, no pueden existir de forma independiente.  Los tipos complejos solo pueden existir como propiedades en tipos de entidad u otros tipos complejos.  
  
-   Los tipos complejos no pueden participar en [asociaciones](../../../../docs/framework/data/adonet/association-type.md).  Los extremos de una asociación no pueden ser tipos complejos y, por consiguiente, no se pueden definir [propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) en los tipos complejos.  
  
## Ejemplo  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio \(DSL\) denominado lenguaje de definición de esquemas conceptuales \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\) para definir los modelos conceptuales.  El código CSDL siguiente define un tipo complejo, Address, con las propiedades de tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 Para definir el tipo complejo `Address` \(arriba\) como una propiedad en un tipo de entidad, debe declarar el tipo de propiedad en la definición del tipo de entidad.  El código CSDL siguiente declara la propiedad `Address` como un tipo complejo en un tipo de entidad \(Publisher\):  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)