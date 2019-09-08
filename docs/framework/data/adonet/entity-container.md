---
title: contenedor de entidades
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 95740fb9d8b357a4fa160af6fdafb139711283cd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795256"
---
# <a name="entity-container"></a>contenedor de entidades
Un *contenedor de entidades* es una agrupación lógica [de conjuntos de entidades](entity-set.md), conjuntos de [asociaciones](association-set.md)e [importaciones de funciones](model-declared-function.md).  
  
 Un contenedor de entidades definido en un modelo conceptual debe cumplir las condiciones siguientes:  
  
- Se debe definir al menos un contenedor de entidades en cada modelo conceptual.  
  
- El contenedor de entidades debe tener un nombre único en cada modelo conceptual.  
  
 Un contenedor de entidades puede definir conjuntos de entidades o de asociaciones que usan tipos de entidad o asociaciones definidos en uno o varios espacios de nombres. Para obtener más información, [vea Entity Data Model: Espacios de nombres.](entity-data-model-namespaces.md)  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.  Para obtener más información, vea el ejemplo siguiente.  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/entity-container/example-model-three-entity-types.gif)  
  
 Aunque el diagrama no proporciona información sobre el contenedor de entidades, el modelo conceptual debe definir un contenedor de entidades. El [Entity Framework ADO.net](./ef/index.md) usa un DSL denominado lenguaje de definición de esquemas conceptuales ([CSDL](./ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El código CSDL siguiente define un contenedor de entidades para el modelo conceptual mostrado en el diagrama anterior. Tenga en cuenta que el nombre del contenedor de entidades se define en un atributo XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
