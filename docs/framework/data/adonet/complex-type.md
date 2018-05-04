---
title: tipo complejo
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: 8daeac8309434b3c4e090d8e75f2de02d63e8b11
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="complex-type"></a>tipo complejo
A *tipo complejo* es una plantilla para definir propiedades enriquecidas y estructuradas para [tipos de entidad](../../../../docs/framework/data/adonet/entity-type.md) u otros tipos complejos. Cada plantilla contiene lo siguiente:  
  
-   Un nombre único. (Necesario)  
  
    > [!NOTE]
    >  El nombre de un tipo complejo no puede coincidir con el nombre de un tipo de entidad dentro del mismo espacio de nombres.  
  
-   Datos en forma de uno o varios [propiedades](../../../../docs/framework/data/adonet/property.md). (Opcional)  
  
    > [!NOTE]
    >  Una propiedad de un tipo complejo puede ser otro tipo complejo.  
  
 Un tipo complejo es similar a un tipo de entidad, ya que un tipo complejo puede llevar una carga de datos en forma de propiedades de tipo primitivo u otros tipos complejos. Sin embargo, existen algunas diferencias clave entre los tipos complejos y los tipos de entidad:  
  
-   Los tipos complejos no tienen identidades y, por consiguiente, no pueden existir de forma independiente. Los tipos complejos solo pueden existir como propiedades en tipos de entidad u otros tipos complejos.  
  
-   Tipos complejos no pueden participar en [asociaciones](../../../../docs/framework/data/adonet/association-type.md). Los extremos de una asociación pueden ser un tipo complejo y, por tanto, [propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) no pueden definirse en tipos complejos.  
  
## <a name="example"></a>Ejemplo  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El código CSDL siguiente define un tipo complejo, Address, con las propiedades de tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 Para definir el tipo complejo `Address` (arriba) como una propiedad en un tipo de entidad, debe declarar el tipo de propiedad en la definición del tipo de entidad. El código CSDL siguiente declara la propiedad `Address` como un tipo complejo en un tipo de entidad (Publisher):  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
