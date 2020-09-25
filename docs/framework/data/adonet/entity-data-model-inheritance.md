---
title: 'Entity Data Model: Herencia'
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: 057040eee411988c46adc9c4cabcfe5f5a185e1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175465"
---
# <a name="entity-data-model-inheritance"></a>Entity Data Model: Herencia

El Entity Data Model (EDM) admite la herencia para los [tipos de entidad](entity-type.md). La herencia en EDM es similar a la herencia para las clases en los lenguajes de programación orientados a objetos. Al igual que sucede con las clases de los lenguajes orientados a objetos, en un modelo conceptual se puede definir un tipo de entidad (un *tipo derivado*) que herede de otro tipo de entidad (el *tipo base*). Sin embargo, a diferencia de las clases de la programación orientada a objetos, en un modelo conceptual, el tipo derivado hereda siempre todas las [propiedades](property.md) y [propiedades de navegación](navigation-property.md) del tipo base. No se pueden reemplazar las propiedades heredadas en un tipo derivado.  
  
 En un modelo conceptual, se pueden crear jerarquías de herencia en las que un tipo derivado hereda de otro tipo derivado. El tipo situado en la parte superior de la jerarquía (el tipo de la jerarquía que no es un tipo derivado) se denomina *tipo raíz*. En una jerarquía de herencia, la [clave de entidad](entity-key.md) debe definirse en el tipo raíz.  
  
 No se pueden crear jerarquías de herencia en las que un tipo derivado hereda de más de un tipo. Por ejemplo, en un modelo conceptual con un tipo de entidad `Book`, se podrían definir tipos derivados `FictionBook` y `NonFictionBook` que hereden de `Book`. Sin embargo, no se podría definir un tipo que herede de los tipos `FictionBook` y `NonFictionBook`.  
  
## <a name="example"></a>Ejemplo  

En el diagrama siguiente se muestra un modelo conceptual con cuatro tipos de entidad: `Book` ,, `FictionBook` `Publisher` y `Author` . El tipo de entidad `FictionBook` es un tipo derivado, que hereda del tipo de entidad `Book`. El tipo `FictionBook` hereda las propiedades `ISBN (Key)`, `Title` y `Revision`, y define una propiedad adicional denominada `Genre`.  
  
 ![Diagrama que muestra un modelo conceptual con cuatro tipos de entidad.](./media/entity-data-model-inheritance/entity-type-inheritance.gif)  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El código CSDL siguiente define un tipo de entidad, `FictionBook`, que hereda del tipo `Book` (como en el diagrama anterior):  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>Consulte también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
