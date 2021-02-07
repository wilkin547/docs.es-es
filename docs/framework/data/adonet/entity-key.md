---
description: 'Más información acerca de: clave de entidad'
title: clave de entidad
ms.date: 03/30/2017
ms.assetid: 0d447a6d-fa7a-4db0-8e7a-fd45e385fca0
ms.openlocfilehash: 588f18a2f76ca11c797b9b2aaab00b090c99e345
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724445"
---
# <a name="entity-key"></a>clave de entidad

Una *clave de entidad* es una [propiedad](property.md) o un conjunto de propiedades de un [tipo de entidad](entity-type.md) que se usan para determinar la identidad. Las propiedades que constituyen una entidad se eligen en tiempo de diseño. Los valores de las propiedades de clave de entidad deben identificar de forma única una instancia de tipo de entidad dentro de un [conjunto de entidades](entity-set.md) en tiempo de ejecución. Las propiedades que constituyen una clave de entidad se deben elegir de tal forma que garanticen la unicidad de las instancias de un conjunto de entidades.  
  
 Los requisitos para que un conjunto de propiedades sea una clave de entidad son los siguientes:  
  
- No puede haber dos claves de entidad idénticas en un conjunto de entidades. Es decir, para dos entidades cualesquiera dentro de un conjunto de entidades, los valores de todas las propiedades que constituyen una clave no pueden ser idénticos. Sin embargo, algunos (pero no todos) los valores que constituyen una clave de entidad pueden ser idénticos.  
  
- Una clave de entidad debe constar de un conjunto de [propiedades de tipo primitivo](entity-data-model-primitive-data-types.md)que no aceptan valores NULL e inmutables.  
  
- Las propiedades que constituyen una clave de entidad para un tipo de entidad determinado no pueden cambiar. No se puede designar más de una clave de entidad posible para un tipo de entidad determinado; no se admiten las claves suplentes.  
  
- Cuando una entidad está implicada en una jerarquía de herencia, la entidad raíz debe contener todas las propiedades que constituyen la clave de entidad, y esta se debe definir en el tipo de entidad raíz. Para obtener más información, vea [Entity Data Model: herencia](entity-data-model-inheritance.md).  
  
## <a name="example"></a>Ejemplo  

 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`. Las propiedades de cada tipo de entidad que constituyen su clave de entidad se denotan con "(Key)". Tenga en cuenta que el tipo de entidad `Author` tiene una clave de entidad que consta de dos propiedades, `Name` y `Address`.  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/entity-key/example-model-three-entity-types.gif)  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El código CSDL siguiente define el tipo de entidad `Book` mostrado en el diagrama anterior. Observe que la clave de entidad se define haciendo referencia a la propiedad `ISBN` del tipo de entidad.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 La propiedad `ISBN` es una opción adecuada para la clave de entidad, ya que el International Standard Book Number (ISBN) permite identificar un libro de manera inequívoca.  
  
 El código CSDL siguiente define el tipo de entidad `Author` mostrado en el diagrama anterior. Observe que la clave de entidad consta de dos propiedades, `Name` y `Address`.  
  
 [!code-xml[EDM_Example_Model#CompositeKeyExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#compositekeyexample)]  
  
 El uso de `Name` y `Address` para la clave de entidad es una opción razonable, ya que no es probable que dos autores con el mismo nombre vivan en la misma dirección. Sin embargo, esta opción no garantiza por completo la existencia de claves de entidad únicas en un conjunto de entidades. En este caso, se recomienda la adición de una propiedad, como `AuthorId`, que se podría usar para identificar un autor de forma inequívoca.  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
