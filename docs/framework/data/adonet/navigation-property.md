---
title: "propiedad de navegación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f5af52532dc534d793e7e8ce72a08c2f7229569b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="navigation-property"></a>propiedad de navegación
A *propiedad de navegación* es una propiedad opcional de un [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) que permite navegar desde un [final](../../../../docs/framework/data/adonet/association-end.md) de un [asociación](../../../../docs/framework/data/adonet/association-type.md) a el otro extremo. A diferencia de otras [propiedades](../../../../docs/framework/data/adonet/property.md), propiedades de navegación no transportan datos.  
  
 Una definición de propiedad de desplazamiento incluye lo siguiente:  
  
-   Un nombre. (Necesario)  
  
-   La asociación que navega. (Necesario)  
  
-   Los extremos de la asociación que navega. (Necesario)  
  
 Las propiedades de navegación son opcionales en los dos tipos de entidad de los extremos de una asociación. Si define una propiedad de navegación en un tipo de entidad del extremo de una asociación, no tiene que definir una propiedad de navegación en el tipo de entidad del otro extremo de la asociación.  
  
 El tipo de datos de una propiedad de navegación está determinado por la [multiplicidad](../../../../docs/framework/data/adonet/association-end-multiplicity.md) de su remoto [extremo de la asociación](../../../../docs/framework/data/adonet/association-end.md). Por ejemplo, supongamos que una propiedad de navegación, `OrdersNavProp`, existe en un tipo de entidad `Customer` y navega a una asociación uno a varios entre `Customer` y `Order`. Dado que el extremo remoto de la asociación para la propiedad de navegación tiene la multiplicidad de muchos (*), su tipo de datos es una colección (de `Order`). De igual forma, si una propiedad de navegación, `CustomerNavProp`, existe en el tipo de entidad `Order`, su tipo de datos sería `Customer`, porque la multiplicidad del extremo remoto es uno (1).  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`. Las propiedades de navegación, `Publisher` y `Authors`, se definen en el tipo de entidad Book. La propiedad de navegación `Books` se define en el tipo de entidad Publisher y el tipo de entidad `Author`.  
  
 ![Modelar con propiedades de navegación](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")  
  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Observe que los atributos de XML permiten comunicar la información necesaria para definir una propiedad de navegación: el atributo `Name` contiene el nombre de la propiedad, `Relationship` contiene el nombre de la asociación que navega y `FromRole` y `ToRole` contienen los extremos de la asociación.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
