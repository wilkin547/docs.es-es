---
title: Entity Data Model
description: En el Entity Data Model se describe la estructura de los datos, independientemente de su forma almacenada, que aborda los desafíos resultantes del almacenamiento de datos en muchas formas.
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: 9323f652d1cfa27d442d45bd01e546f3b81d7e80
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200776"
---
# <a name="entity-data-model"></a>Entity Data Model

Entity Data Model (EDM) es un conjunto de conceptos que describen la estructura de los datos, independientemente del formato en el que estén almacenados. EDM se basa en el modelo entidad-relación (Entity-Relationship Model) descrito por Peter Chen en 1976, pero también incorpora nuevas funciones y amplía sus usos tradicionales.  
  
 EDM soluciona los desafíos que plantea el tener datos almacenados en muchos formatos. Considere, por ejemplo, un negocio que almacena los datos en bases de datos relacionales, archivos de texto, archivos XML, hojas de cálculo e informes. Esto presenta importantes desafíos en el modelado de datos, el diseño de aplicaciones y el acceso a los datos. Al diseñar una aplicación orientada a datos, el desafío consiste en escribir un código eficaz y que se pueda mantener sin sacrificar la eficacia del acceso a los datos, el almacenamiento y la escalabilidad. Cuando los datos tienen una estructura relacional, el acceso a los datos, el almacenamiento y la escalabilidad resultan muy eficaces, pero es más difícil escribir un código eficaz y que se pueda mantener. Cuando los datos tienen una estructura de objeto, se invierten las ventajas; es decir, la escritura de un código eficaz y que se pueda mantener se consigue a costa de la eficacia en el acceso a los datos, el almacenamiento y la escalabilidad. Aunque es posible encontrar el equilibrio adecuado entre ambos métodos, surgen nuevos desafíos cuando se mueven los datos de un formato a otro. Entity Data Model resuelve estos desafíos describiendo la estructura de los datos en forma de entidades y relaciones que son independientes de cualquier esquema de almacenamiento. Esto hace que el formato en el que están almacenados los datos sea irrelevante a la hora de diseñar y desarrollar las aplicaciones. Y, dado que las entidades y las relaciones describen la estructura de los datos tal como se usan en una aplicación (no el formato en el que están almacenados), pueden evolucionar al mismo tiempo que la aplicación.  
  
 Un modelo conceptual (`conceptual model`) es una representación específica de la estructura de los datos en forma de entidades y relaciones, y normalmente se define mediante un lenguaje específico de dominio (DSL) que implementa los conceptos de EDM. El [lenguaje de definición de esquemas conceptuales (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) es un ejemplo de este tipo de lenguaje específico de dominio. Las entidades y relaciones descritas en un modelo conceptual se pueden considerar como abstracciones de objetos y asociaciones en una aplicación. Esto permite a los desarrolladores centrarse en el modelo conceptual sin tener que preocuparse por el esquema de almacenamiento, así como escribir el código teniendo en cuenta la eficacia y el mantenimiento. Mientras tanto, los diseñadores del esquema de almacenamiento pueden centrarse en la eficacia en el acceso a los datos, el almacenamiento y la escalabilidad.  
  
## <a name="in-this-section"></a>En esta sección  

 Los temas de esta sección describen los conceptos de Entity Data Model. Cualquier ADSL que implemente EDM debe incluir los conceptos descritos a continuación. Tenga en cuenta que el [Entity Framework ADO.net](./ef/index.md) utiliza CSDL para definir los modelos conceptuales. Para obtener más información, consulta [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).  
  
 [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)  
  
 [Entity Data Model: Espacios de nombres](entity-data-model-namespaces.md)  
  
 [Entity Data Model: tipos de datos primitivos](entity-data-model-primitive-data-types.md)  
  
 [Entity Data Model: Herencia](entity-data-model-inheritance.md)  
  
 [extremo de asociación](association-end.md)  
  
 [multiplicidad de extremo de asociación](association-end-multiplicity.md)  
  
 [conjunto de asociaciones](association-set.md)  
  
 [extremo del conjunto de asociaciones](association-set-end.md)  
  
 [tipo de asociación](association-type.md)  
  
 [tipo complejo](complex-type.md)  
  
 [contenedor de entidades](entity-container.md)  
  
 [clave de entidad](entity-key.md)  
  
 [conjunto de entidades](entity-set.md)  
  
 [tipo de entidad](entity-type.md)  
  
 [agrupa](facet.md)  
  
 [propiedad de clave externa](foreign-key-property.md)  
  
 [función declarada por el modelo](model-declared-function.md)  
  
 [función definida por el modelo](model-defined-function.md)  
  
 [propiedad de navegación](navigation-property.md)  
  
 [property](property.md)  
  
 [restricción de integridad referencial](referential-integrity-constraint.md)  
  
## <a name="see-also"></a>Consulte también

- [ADO.NET Entity Data Model herramientas](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [.edmx, Información general sobre el archivo](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Especificación CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
