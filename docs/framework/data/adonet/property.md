---
title: propiedad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 50cd2f2678d304af8b898380645424e0635891d2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="property"></a>propiedad
*Propiedades* son los bloques de creación fundamentales de [tipos de entidad](../../../../docs/framework/data/adonet/entity-type.md) y [tipos complejos](../../../../docs/framework/data/adonet/complex-type.md). Las propiedades definen la forma y características de datos que una instancia del tipo de entidad o la instancia del tipo complejo contendrá. Las propiedades en un modelo conceptual son análogas a las propiedades definidas en una clase. Del mismo modo que las propiedades en una clase definen la forma de la clase y proporcionan información sobre los objetos, las propiedades en un modelo conceptual definen la forma de un tipo de entidad y proporcionan información sobre las instancias del tipo de entidad.  
  
> [!NOTE]
>  Las propiedades, tal y como se describen en este tema, son diferentes de las propiedades de navegación. Para obtener más información, consulte [propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md).  
  
 Una definición de propiedad contiene la siguiente información:  
  
-   nombre de propiedad. (Necesario)  
  
-   Un tipo de propiedad. (Necesario)  
  
-   Un conjunto de [facetas](../../../../docs/framework/data/adonet/facet.md). (Opcional)  
  
 Una propiedad puede contener datos primitivos (como una cadena, un entero o un valor booleano) o estructura los datos (como un tipo complejo). Las propiedades de tipo primitivo también se denominan propiedades escalares. Para obtener más información, consulte [Entity Data Model: tipos de datos primitivos](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).  
  
> [!NOTE]
>  Un tipo complejo puede, por sí mismo, tener propiedades complejas.  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`. Cada tipo de entidad tiene varias propiedades, aunque la información de tipo para cada propiedad no se muestra en el diagrama. Propiedades que son [claves de entidad](../../../../docs/framework/data/adonet/entity-key.md) se denotan con (Key).  
  
 ![Ejemplo de modelo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. En el siguiente CSDL se define el tipo de entidad `Book` (como se muestra en el diagrama anterior) y se indica el tipo y nombre de cada propiedad utilizando atributos XML. Una faceta opcional, `Nullable`, también se define utilizando un atributo de XML.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Es posible que una de las propiedades mostradas en el diagrama sea una propiedad de tipo complejo. Por ejemplo, la propiedad `Address` en el tipo de entidad `Publisher` podría ser una propiedad de tipo complejo compuesta de varias propiedades escalares, como `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`. La representación CSDL de un tipo complejo como el anterior sería como sigue:  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
