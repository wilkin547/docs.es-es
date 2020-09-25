---
title: propiedad
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: 6aeb29c5aa608987466ec858416a4ac141ff1da3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180925"
---
# <a name="property"></a>propiedad

*Las propiedades* son los bloques de creación fundamentales de [tipos de entidad](entity-type.md) y [tipos complejos](complex-type.md). Las propiedades definen la forma y características de datos que una instancia del tipo de entidad o la instancia del tipo complejo contendrá. Las propiedades en un modelo conceptual son análogas a las propiedades definidas en una clase. Del mismo modo que las propiedades en una clase definen la forma de la clase y proporcionan información sobre los objetos, las propiedades en un modelo conceptual definen la forma de un tipo de entidad y proporcionan información sobre las instancias del tipo de entidad.  
  
> [!NOTE]
> Las propiedades, tal y como se describen en este tema, son diferentes de las propiedades de navegación. Para obtener más información, vea [propiedades de navegación](navigation-property.md).  
  
 Una definición de propiedad contiene la siguiente información:  
  
- nombre de propiedad. (Requerido)  
  
- Un tipo de propiedad. (Requerido)  
  
- Un conjunto de [aspectos](facet.md). (Opcional)  
  
 Una propiedad puede contener datos primitivos (como una cadena, un entero o un valor booleano) o estructura los datos (como un tipo complejo). Las propiedades de tipo primitivo también se denominan propiedades escalares. Para obtener más información, vea [Entity Data Model: tipos de datos primitivos](entity-data-model-primitive-data-types.md).  
  
> [!NOTE]
> Un tipo complejo puede, por sí mismo, tener propiedades complejas.  
  
## <a name="example"></a>Ejemplo  

 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`. Cada tipo de entidad tiene varias propiedades, aunque la información de tipo para cada propiedad no se muestra en el diagrama. Las propiedades que son [claves de entidad](entity-key.md) se denotan con (Key).  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/property/example-model-three-entity-types.gif)  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. En el siguiente CSDL se define el tipo de entidad `Book` (como se muestra en el diagrama anterior) y se indica el tipo y nombre de cada propiedad utilizando atributos XML. Una faceta opcional, `Nullable`, también se define utilizando un atributo de XML.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Es posible que una de las propiedades mostradas en el diagrama sea una propiedad de tipo complejo. Por ejemplo, la propiedad `Address` en el tipo de entidad `Publisher` podría ser una propiedad de tipo complejo compuesta de varias propiedades escalares, como `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`. La representación CSDL de un tipo complejo como el anterior sería como sigue:  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a>Consulte también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
