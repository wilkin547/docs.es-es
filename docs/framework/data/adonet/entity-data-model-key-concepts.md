---
description: 'Más información acerca de: Entity Data Model conceptos clave'
title: Conceptos clave de Entity Data Model
ms.date: 03/30/2017
ms.assetid: c635a16d-6674-45aa-9344-dcb7df992bab
ms.openlocfilehash: 4b97a39a5989689662db7be92b259b9a08d84cc7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672803"
---
# <a name="entity-data-model-key-concepts"></a>Conceptos clave de Entity Data Model

El Entity Data Model (EDM) usa tres conceptos clave para describir la estructura de los datos: el *tipo de entidad*, el *tipo de asociación* y la *propiedad*. Estos son los conceptos más importantes para describir la estructura de datos en cualquier implementación de EDM.  
  
## <a name="entity-type"></a>Tipo de entidad  

 El [tipo de entidad](entity-type.md) es el bloque de creación fundamental para describir la estructura de los datos con el Entity Data Model. En un modelo conceptual, los tipos de entidad se construyen a partir de [propiedades](property.md) y describen la estructura de conceptos de nivel superior, como clientes y pedidos en una aplicación empresarial. Del mismo modo que una definición de clase en un programa es una plantilla para las instancias de la clase, un tipo de entidad es una plantilla para las entidades. Una entidad representa un objeto concreto (como un cliente o pedido concreto). Cada entidad debe tener una [clave de entidad](entity-key.md) única dentro de un [conjunto de entidades](entity-set.md).  Un conjunto de entidades es una colección de instancias de un tipo de entidad concreto. Los conjuntos de entidades (y los [conjuntos de asociaciones](association-set.md)) se agrupan de forma lógica en un [contenedor de entidades](entity-container.md).  
  
 Los tipos de entidad admiten la herencia: es decir, un tipo de entidad se puede derivar de otro. Para obtener más información, vea [Entity Data Model: herencia](entity-data-model-inheritance.md).  
  
## <a name="association-type"></a>Tipo de asociación  

 Un [tipo de asociación](association-type.md) (también denominado Asociación) es el bloque de creación fundamental para describir las relaciones en el Entity Data Model. En un modelo conceptual, una asociación representa una relación entre dos tipos de entidad (como Customer y Order). Cada asociación tiene dos [extremos de asociación](association-end.md) que especifican los tipos de entidad implicados en la asociación. Cada extremo de la asociación también especifica una [multiplicidad de extremo de asociación](association-end-multiplicity.md) que indica el número de entidades que pueden estar en ese extremo de la asociación. Una multiplicidad de extremo de asociación puede tener un valor de uno (1), cero o uno (0.. 1) o varios ( \* ). Se puede tener acceso a las entidades de un extremo de una asociación a través de [las propiedades de navegación](navigation-property.md)o a través de claves externas si se exponen en un tipo de entidad. Para obtener más información, consulte [Foreign Key Property](foreign-key-property.md).  
  
 En una aplicación, una instancia de una asociación representa una asociación concreta (como por ejemplo una asociación entre una instancia Customer y una instancia Order). Las instancias de asociación se agrupan lógicamente en un [conjunto de asociaciones](association-set.md). Los conjuntos de asociaciones (y los [conjuntos de entidades](entity-set.md)) se agrupan de forma lógica en un [contenedor de entidades](entity-container.md).  
  
## <a name="property"></a>Propiedad  

 Los [tipos de entidad](entity-type.md) contienen [propiedades](property.md) que definen su estructura y sus características. Por ejemplo, un tipo de entidad Customer puede tener propiedades como CustomerId, Name y Address.  
  
 Las propiedades en un modelo conceptual son análogas a las propiedades definidas en una clase en un programa. Del mismo modo que las propiedades en una clase definen la forma de la clase y proporcionan información sobre los objetos, las propiedades en un modelo conceptual definen la forma de un tipo de entidad y proporcionan información sobre las instancias del tipo de entidad.  
  
 Una propiedad puede contener datos primitivos (como una cadena, un entero o un valor booleano) o estructura los datos (como un tipo complejo). Para obtener más información, vea [Entity Data Model: tipos de datos primitivos](entity-data-model-primitive-data-types.md).  
  
## <a name="representations-of-a-conceptual-model"></a>Representaciones de un modelo conceptual  

 Un *modelo conceptual* es una representación específica de la estructura de algunos datos como entidades y relaciones. Una manera de representar un modelo conceptual es con un diagrama. El siguiente diagrama representa un modelo conceptual con tres tipos de entidad (`Book`, `Publisher` y `Author`) y dos asociaciones (`PublishedBy` y `WrittenBy`):  
  
 ![Diagrama que muestra un modelo conceptual con tres tipos de entidad.](./media/entity-data-model-key-concepts/conceptual-model-entity-types-associations.gif)  
  
 Esta representación, sin embargo, tiene algunas limitaciones a la hora de representar algunos detalles acerca del modelo. Por ejemplo, la información sobre el tipo de propiedad y el conjunto de entidades no se representa en el diagrama. La riqueza de un modelo conceptual se puede representar con mayor claridad mediante un lenguaje específico de dominio (ADSL). El [Entity Framework ADO.net](./ef/index.md) usa un DSL basado en XML denominado *lenguaje de definición de esquemas conceptuales* ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. A continuación se muestra la definición CSDL del modelo conceptual del diagrama anterior:  
  
 [!code-xml[EDM_Example_Model#EDMExampleCSDL](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#edmexamplecsdl)]  
  
## <a name="see-also"></a>Vea también

- [Entity Data Model](entity-data-model.md)
