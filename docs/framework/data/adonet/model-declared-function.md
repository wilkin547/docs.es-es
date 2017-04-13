---
title: "funci&#243;n declarada por el modelo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# funci&#243;n declarada por el modelo
Una *función declarada por modelo* es una función que se declara en un modelo conceptual, pero que no se define en ese modelo conceptual.  La función se podría definir en el entorno de almacenamiento u hospedaje.  Por ejemplo, una función declarada por modelo se podría asignar a una función definida en una base de datos, exponiendo así la funcionalidad de servidor en el modelo conceptual.  
  
 La declaración de una función declarada por modelo contiene la siguiente información:  
  
-   Nombre de la función.  \(Necesario\)  
  
-   El tipo del valor devuelto.  \(Opcional\)  
  
    > [!NOTE]
    >  Si no se especifica ningún valor devuelto, el tipo de valor devuelto es void.  
  
-   Información de parámetro, incluidos el tipo y el nombre de parámetro.  \(Opcional\)  
  
## Ejemplo  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio \(DSL\) denominado lenguaje de definición de esquemas conceptuales \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\) para definir los modelos conceptuales.  En CSDL, una implementación de una función declarada por modelo es una [importación de función](http://msdn.microsoft.com/es-es/125704ae-56c7-4233-80b7-389a10f3a65d).  El siguiente CSDL define un contenedor de la entidad con una definición de importación de función.  Tenga en cuenta que el tipo de valor devuelto es void porque no se especifica ningún tipo de valor devuelto.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)