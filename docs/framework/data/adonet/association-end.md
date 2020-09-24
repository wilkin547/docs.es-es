---
title: extremo de asociación
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 00e3a7d855957ae539ea652dc8cde3ed8841dda5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153448"
---
# <a name="association-end"></a>extremo de asociación

Un *extremo de asociación* identifica el [tipo de entidad](entity-type.md) en un extremo de una [Asociación](association-type.md) y el número de instancias de tipo de entidad que pueden existir en ese extremo de una asociación. Los extremos de asociación se definen como parte de una asociación, y esta debe tener exactamente dos extremos. [Las propiedades de navegación](navigation-property.md) permiten la navegación de un extremo de asociación al otro.  
  
 Una definición de extremo de asociación contiene la información siguiente:  
  
- Uno de los tipos de entidad implicados en la asociación. (Requerido)  
  
    > [!NOTE]
    > En una asociación determinada, el tipo de entidad especificado para cada extremo de la asociación puede ser el mismo. Esto crea una auto-asociación.  
  
- Una [multiplicidad de extremo de asociación](association-end-multiplicity.md) que indica el número de instancias de tipo de entidad que pueden estar en un extremo de la asociación. Una multiplicidad de extremo de asociación puede tener un valor de uno (1), cero o uno (0.. 1) o varios ( \* ).  
  
- Nombre para el extremo de la asociación. (Opcional)  
  
- Información sobre las operaciones que se realizan en el extremo de la asociación, como por ejemplo la eliminación en cascada. (Opcional)  
  
## <a name="example"></a>Ejemplo  

 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`. Los extremos de asociación para la asociación `PublishedBy` son los tipos de entidad `Book` y `Publisher`. La multiplicidad del `Publisher` extremo es uno (1) y la multiplicidad del `Book` extremo es muchos ( \* ), lo que indica que un publicador publica muchos libros y un libro publicado por un publicador.  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-end/example-model-three-entity-types.gif)  
  
 El Entity Framework ADO.NET usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El CSDL siguiente define la asociación `PublishedBy` mostrada en el diagrama anterior. Tenga en cuenta que el tipo, el nombre y la multiplicidad de cada extremo de la asociación se especifican mediante atributos XML (los atributos `Type`, `Role` y `Multiplicity`, respectivamente). La información adicional sobre las operaciones realizadas en un extremo se especifica mediante un elemento XML (el elemento `OnDelete`-). En este caso, si se elimina un editor, también se eliminan todos los libros asociados.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
