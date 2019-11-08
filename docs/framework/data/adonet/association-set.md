---
title: conjunto de asociaciones
ms.date: 03/30/2017
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
ms.openlocfilehash: e279322f9e950cd4359db8c6dce39bfc46d188f6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732368"
---
# <a name="association-set"></a>conjunto de asociaciones
Un *conjunto de asociaciones* es un contenedor lógico para las instancias de [Asociación](association-type.md) del mismo tipo. Un conjunto de asociaciones no es una construcción del modelado de datos; es decir, no describe la estructura de datos o relaciones. En su lugar, un conjunto de asociaciones proporciona una construcción para que un entorno de hospedaje o de almacenamiento (como Common Language Runtime o una base de datos de SQL Server) agrupe las instancias de asociaciones a fin de que se puedan asignar a un almacén de datos.  
  
 Un conjunto de asociaciones se define dentro de un [contenedor de entidades](entity-container.md), que es una agrupación lógica de [conjuntos de entidades](entity-set.md) y conjuntos de asociaciones.  
  
 Una definición de un conjunto de asociaciones contiene la información siguiente:  
  
- El nombre del conjunto de asociaciones. (Necesario)  
  
- La asociación cuyas instancias contendrá. (Necesario)  
  
- Dos [extremos del conjunto de asociaciones](association-set-end.md).  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`. Aunque la información sobre los conjuntos de asociaciones no se muestra en el diagrama, el diagrama siguiente muestra un ejemplo de conjuntos de asociaciones y conjuntos de entidades basados en este modelo.  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-set/example-model-three-entity-types.gif)  
  
 El siguiente ejemplo muestra un conjunto de asociaciones (`PublishedBy` y dos conjuntos de entidades (`Books` y `Publishers`) basados en el modelo conceptual mostrado anteriormente. BI en el conjunto de entidades `Books` representa una instancia del tipo de entidad `Book` en tiempo de ejecución. De forma similar, PJ representa una instancia de `Publisher` en el conjunto de entidades `Publishers`. BiPj representa una instancia de la Asociación `PublishedBy` en el conjunto de asociaciones `PublishedBy`.  
  
 ![Captura de pantalla que muestra un ejemplo de conjuntos.](./media/association-set/sets-example-association.gif)  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El siguiente CSDL define un contenedor de entidad con un conjunto de asociaciones para cada asociación en el diagrama anterior. Observe que el nombre y asociación para cada conjunto de asociaciones se definen utilizando los atributos XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 Es posible definir varios conjuntos de asociaciones por asociación, siempre y cuando no haya dos conjuntos de asociaciones que compartan un [extremo del conjunto de asociaciones](association-set-end.md). En el siguiente CSDL se define un contenedor de entidades con dos conjuntos de asociaciones para la asociación `WrittenBy`. Observe que se han definido varios conjuntos de entidades para los tipos de entidad `Book` y `Author` y que ningún conjunto de asociaciones comparte un extremo del conjunto de asociaciones.  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [propiedad de clave externa](foreign-key-property.md)
