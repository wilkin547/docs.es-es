---
title: extremo del conjunto de asociaciones
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: f7ec1ca6fcdf299b9fcfc78f299ea4c6c5267cd3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738618"
---
# <a name="association-set-end"></a>extremo del conjunto de asociaciones
Un *extremo del conjunto de asociaciones* identifica el [tipo de entidad](entity-type.md) y el [conjunto de entidades](entity-set.md) al final de un [conjunto de asociaciones](association-set.md). Los extremos de conjuntos de asociaciones se definen como parte de un conjunto de asociaciones, que debe tener exactamente dos extremos.  
  
 Una definición de extremo de conjunto de asociaciones contiene la información siguiente:  
  
- Uno de los tipos de entidad implicados en el conjunto de asociaciones. (Necesario)  
  
- El conjunto de entidades para el tipo de entidad implicado en el conjunto de asociaciones. (Necesario)  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `WrittenBy` y `PublishedBy`.  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-set-end/example-model-three-entity-types.gif)  
  
 El diagrama siguiente muestra un conjunto de asociaciones (`PublishedBy` y dos conjuntos de entidades (`Books` y `Publishers`) basados en el modelo conceptual mostrado anteriormente. Los extremos del conjunto de asociaciones son los conjuntos de entidades `Books` y `Publishers`. BI en el conjunto de entidades `Books` representa una instancia del tipo de entidad `Book` en tiempo de ejecución. De forma similar, PJ representa una instancia de `Publisher` en el conjunto de entidades `Publishers`. BiPj representa una instancia de la Asociación `PublishedBy` en el conjunto de asociaciones `PublishedBy`.  
  
 ![Captura de pantalla que muestra un ejemplo de conjuntos.](./media/association-set-end/sets-example-association.gif)  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un DSL denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El siguiente CSDL define un contenedor de entidad con un conjunto de asociaciones para cada asociación en el diagrama anterior. Observe que los extremos del conjunto de asociaciones se definen como parte de cada definición del conjunto de asociaciones.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
