---
title: Entity Data Model
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: e76527b497434ada06762fcab931522fffa2a16b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385599"
---
# <a name="entity-data-model"></a>Entity Data Model
Entity Data Model (EDM) es un conjunto de conceptos que describen la estructura de los datos, independientemente del formato en el que estén almacenados. EDM se basa en el modelo entidad-relación (Entity-Relationship Model) descrito por Peter Chen en 1976, pero también incorpora nuevas funciones y amplía sus usos tradicionales.  
  
 EDM soluciona los desafíos que plantea el tener datos almacenados en muchos formatos. Considere, por ejemplo, un negocio que almacena los datos en bases de datos relacionales, archivos de texto, archivos XML, hojas de cálculo e informes. Esto presenta importantes desafíos en el modelado de datos, el diseño de aplicaciones y el acceso a los datos. Al diseñar una aplicación orientada a datos, el desafío consiste en escribir un código eficaz y que se pueda mantener sin sacrificar la eficacia del acceso a los datos, el almacenamiento y la escalabilidad. Cuando los datos tienen una estructura relacional, el acceso a los datos, el almacenamiento y la escalabilidad resultan muy eficaces, pero es más difícil escribir un código eficaz y que se pueda mantener. Cuando los datos tienen una estructura de objeto, se invierten las ventajas; es decir, la escritura de un código eficaz y que se pueda mantener se consigue a costa de la eficacia en el acceso a los datos, el almacenamiento y la escalabilidad. Aunque es posible encontrar el equilibrio adecuado entre ambos métodos, surgen nuevos desafíos cuando se mueven los datos de un formato a otro. Entity Data Model resuelve estos desafíos describiendo la estructura de los datos en forma de entidades y relaciones que son independientes de cualquier esquema de almacenamiento. Esto hace que el formato en el que están almacenados los datos sea irrelevante a la hora de diseñar y desarrollar las aplicaciones. Y, dado que las entidades y las relaciones describen la estructura de los datos tal como se usan en una aplicación (no el formato en el que están almacenados), pueden evolucionar al mismo tiempo que la aplicación.  
  
 Un modelo conceptual (`conceptual model`) es una representación específica de la estructura de los datos en forma de entidades y relaciones, y normalmente se define mediante un lenguaje específico de dominio (DSL) que implementa los conceptos de EDM. [Lenguaje de definición de esquemas conceptuales (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) es un ejemplo de este tipo de lenguaje específico de dominio. Las entidades y relaciones descritas en un modelo conceptual se pueden considerar como abstracciones de objetos y asociaciones en una aplicación. Esto permite a los desarrolladores centrarse en el modelo conceptual sin tener que preocuparse por el esquema de almacenamiento, así como escribir el código teniendo en cuenta la eficacia y el mantenimiento. Mientras tanto, los diseñadores del esquema de almacenamiento pueden centrarse en la eficacia en el acceso a los datos, el almacenamiento y la escalabilidad.  
  
## <a name="in-this-section"></a>En esta sección  
 Los temas de esta sección describen los conceptos de Entity Data Model. Cualquier ADSL que implemente EDM debe incluir los conceptos descritos a continuación. Tenga en cuenta que el [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa CSDL para definir los modelos conceptuales. Para obtener más información, consulte [especificación de CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).  
  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [Entity Data Model: Espacios de nombres](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [Entity Data Model: Tipos de datos primitivos](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [Entity Data Model: Herencia](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [extremo de asociación](../../../../docs/framework/data/adonet/association-end.md)  
  
 [multiplicidad de extremo de asociación](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [conjunto de asociaciones](../../../../docs/framework/data/adonet/association-set.md)  
  
 [extremo del conjunto de asociaciones](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [tipo de asociación](../../../../docs/framework/data/adonet/association-type.md)  
  
 [tipo complejo](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [contenedor de entidades](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [conjunto de entidades](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [facet](../../../../docs/framework/data/adonet/facet.md)  
  
 [propiedad de clave externa](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [función declarada por el modelo](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [función definida por el modelo](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [propiedad de navegación](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [propiedad](../../../../docs/framework/data/adonet/property.md)  
  
 [restricción de integridad referencial](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a>Vea también  
 [Herramientas de Entity Data Model de ADO.NET](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [Introducción al archivo .edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Especificación CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)
