---
description: 'Más información acerca de: multiplicidad de extremo de asociación'
title: multiplicidad de extremo de asociación
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 4b708406192e8a6e34119b47261d8986829f2a43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697704"
---
# <a name="association-end-multiplicity"></a>multiplicidad de extremo de asociación

La *multiplicidad de extremo de asociación* define el número de instancias de tipo de [entidad](entity-type.md) que pueden estar en un extremo de una [Asociación](association-type.md).  
  
 Una multiplicidad de extremo de asociación puede tener uno de los valores siguientes:  
  
- uno (1): indica que existe exactamente una instancia de tipo de entidad en el extremo de la asociación.  
  
- cero o uno (0..1): indica que pueden existir cero o una instancia de tipo de entidad en el extremo de la asociación.  
  
- Many ( \* ): indica que hay cero, una o más instancias de tipo de entidad en el extremo de la asociación.  
  
 Normalmente, una asociación se caracteriza por sus multiplicidades de extremo de asociación. Por ejemplo, si los extremos de una asociación tienen multiplicidades uno (1) y varios ( \* ), la asociación se denomina una asociación uno a varios. En el ejemplo siguiente, la asociación `PublishedBy` es una asociación uno a varios (un publicador publica muchos libros y un libro solo puede ser publicado por un publicador). La asociación `WrittenBy` es una asociación varios a varios (un libro puede tener varios autores y un autor puede escribir varios libros).  
  
## <a name="example"></a>Ejemplo  

 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`. Los extremos de asociación para la asociación `PublishedBy` son los tipos de entidad `Book` y `Publisher`. La multiplicidad del `Publisher` extremo es uno (1) y la multiplicidad del `Book` extremo es muchos ( \* ).  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 El Entity Framework ADO.NET usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El código CSDL siguiente define la asociación `PublishedBy` mostrada en el diagrama anterior:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
