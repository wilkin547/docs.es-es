---
title: tipo complejo
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: ef20de6a9e72d3123d745ef5501ecdb7fa63967d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203792"
---
# <a name="complex-type"></a>tipo complejo

Un *tipo complejo* es una plantilla para definir propiedades enriquecidas y estructuradas en [tipos de entidad](entity-type.md) o en otros tipos complejos. Cada plantilla contiene lo siguiente:  
  
- Un nombre único. (Requerido)  
  
    > [!NOTE]
    > El nombre de un tipo complejo no puede coincidir con el nombre de un tipo de entidad dentro del mismo espacio de nombres.  
  
- Datos en forma de una o más [propiedades](property.md). (Opcional).  
  
    > [!NOTE]
    > Una propiedad de un tipo complejo puede ser otro tipo complejo.  
  
 Un tipo complejo es similar a un tipo de entidad, ya que un tipo complejo puede llevar una carga de datos en forma de propiedades de tipo primitivo u otros tipos complejos. Sin embargo, existen algunas diferencias clave entre los tipos complejos y los tipos de entidad:  
  
- Los tipos complejos no tienen identidades y, por consiguiente, no pueden existir de forma independiente. Los tipos complejos solo pueden existir como propiedades en tipos de entidad u otros tipos complejos.  
  
- Los tipos complejos no pueden participar en [asociaciones](association-type.md). Ninguno de los extremos de una asociación puede ser un tipo complejo y, por lo tanto, [las propiedades de navegación](navigation-property.md) no se pueden definir en tipos complejos.  
  
## <a name="example"></a>Ejemplo  

 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El código CSDL siguiente define un tipo complejo, Address, con las propiedades de tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 Para definir el tipo complejo `Address` (arriba) como una propiedad en un tipo de entidad, debe declarar el tipo de propiedad en la definición del tipo de entidad. El código CSDL siguiente declara la propiedad `Address` como un tipo complejo en un tipo de entidad (Publisher):  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a>Consulte también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
