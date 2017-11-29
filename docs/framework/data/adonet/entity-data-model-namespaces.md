---
title: 'Entity Data Model: Espacios de nombres'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3e473453576f04e89b58806c5140e29855d7d022
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="entity-data-model-namespaces"></a>Entity Data Model: Espacios de nombres
Un espacio de nombres en Entity Data Model (EDM) es un contenedor abstracto para [tipos de entidad](../../../../docs/framework/data/adonet/entity-type.md), [tipos complejos](../../../../docs/framework/data/adonet/complex-type.md), y [asociaciones](../../../../docs/framework/data/adonet/association-type.md). Los espacios de nombres en EDM son similares a los de un lenguaje de programación: proporcionan el contexto para los objetos que contienen, así como una manera de eliminar la ambigüedad de objetos que tienen el mismo nombre (pero que contienen espacios de nombres diferentes).  
  
## <a name="example"></a>Ejemplo  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. En el siguiente código CSDL se utiliza un espacio de nombres para identificar un tipo que se define en un modelo conceptual diferente. En el ejemplo se define un tipo de entidad (`Publisher`) con una propiedad de tipo complejo (`Address`) que se importa del espacio de nombres `ExtendedBooksModel`. Observe que el elemento `Using` indica que se ha importado un espacio de nombres. Observe también que el tipo de la propiedad `Address` se define utilizando su nombre completo (`ExtendedBooksModel.Address`), lo que indica que este tipo se define en el espacio de nombres `ExtendedBooksModel`.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos básicos de modelo de datos de entidad](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
