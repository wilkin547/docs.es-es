---
title: 'Propiedad de navegación: ADO.NET'
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: b57ecf9329aa9ea8afc07507613c9e3961bfd0a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772273"
---
# <a name="navigation-property"></a>Propiedad de navegación

Un *propiedad de navegación* es una propiedad opcional en un [tipo de entidad](entity-type.md) que permite navegar desde un [final](association-end.md) de un [asociación](association-type.md) a el otro extremo. A diferencia de otras [propiedades](property.md), las propiedades de navegación no transportan datos.

Una definición de propiedad de desplazamiento incluye lo siguiente:

- Un nombre. (Necesario)

- La asociación que navega. (Necesario)

- Los extremos de la asociación que navega. (Necesario)

Las propiedades de navegación son opcionales en los dos tipos de entidad de los extremos de una asociación. Si define una propiedad de navegación en un tipo de entidad del extremo de una asociación, no tiene que definir una propiedad de navegación en el tipo de entidad del otro extremo de la asociación.

El tipo de datos de una propiedad de navegación viene determinada por la [multiplicidad](association-end-multiplicity.md) de su configuración remota [extremo de asociación](association-end.md). Por ejemplo, supongamos que una propiedad de navegación, `OrdersNavProp`, existe en un tipo de entidad `Customer` y navega a una asociación uno a varios entre `Customer` y `Order`. Dado que el extremo remoto de asociación para la propiedad de navegación tiene la multiplicidad de muchos (\*), su tipo de datos es una colección (de `Order`). De igual forma, si una propiedad de navegación, `CustomerNavProp`, existe en el tipo de entidad `Order`, su tipo de datos sería `Customer`, porque la multiplicidad del extremo remoto es uno (1).

## <a name="example"></a>Ejemplo

El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`. Las propiedades de navegación, `Publisher` y `Authors`, se definen en el tipo de entidad Book. La propiedad de navegación `Books` se define en el tipo de entidad Publisher y el tipo de entidad `Author`.

 ![Diagrama que muestra un modelo conceptual con tres tipos de entidad.](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

El [ADO.NET Entity Framework](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](./ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

Tenga en cuenta que los atributos XML se utilizan para comunicar la información necesaria para definir una propiedad de navegación: El atributo `Name` contiene el nombre de la propiedad, `Relationship` contiene el nombre de la asociación que navega y `FromRole` y `ToRole` contienen los extremos de la asociación.

## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [Las relaciones, las propiedades de navegación y las claves externas](/ef/ef6/fundamentals/relationships)
