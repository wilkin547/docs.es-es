---
title: conjunto de entidades
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: 6286d3707a8506e7a389359a5aa361c152e75212
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194798"
---
# <a name="entity-set"></a>conjunto de entidades

Un *conjunto de entidades* es un contenedor lógico para las instancias de un [tipo de entidad](entity-type.md) y las instancias de cualquier tipo derivado de ese tipo de entidad. (Para obtener información sobre los tipos derivados, vea [Entity Data Model: herencia](entity-data-model-inheritance.md)). La relación entre un tipo de entidad y un conjunto de entidades es análoga a la relación entre una fila y una tabla en una base de datos relacional: como una fila, un tipo de entidad describe la estructura de datos y, como una tabla, un conjunto de entidades contiene instancias de una estructura determinada. Un conjunto de entidades no es una construcción de modelado de datos, ya que no describe la estructura de los datos. En su lugar, un conjunto de entidades proporciona una construcción para que un entorno de hospedaje o de almacenamiento (como Common Language Runtime o una base de datos de SQL Server) agrupe las instancias del tipo de entidad y se puedan asignar a un almacén de datos.  
  
 Un conjunto de entidades se define dentro de un [contenedor de entidades](entity-container.md), que es una agrupación lógica de conjuntos de entidades y [conjuntos de asociaciones](association-set.md).  
  
 Para que una instancia de tipo de entidad exista en un conjunto de entidades, deben cumplirse las condiciones siguientes:  
  
- El tipo de la instancia puede ser el mismo que el tipo de entidad en el que se basa el conjunto de entidades, o un subtipo del tipo de entidad.  
  
- La [clave de entidad](entity-key.md) para la instancia es única en el conjunto de entidades.  
  
- La instancia no existe en ningún otro conjunto de entidades.  
  
    > [!NOTE]
    > Se pueden definir varios conjuntos de entidades usando el mismo tipo de entidad, pero una instancia de un tipo de entidad determinado solo puede existir en un conjunto de entidades.  
  
 No es necesario definir un conjunto de entidades para cada tipo de entidad de un modelo conceptual.  
  
## <a name="example"></a>Ejemplo  

 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/entity-set/example-model-three-entity-types.gif)  
  
 El diagrama siguiente muestra dos conjuntos de entidades (`Books` y `Publishers`) y un conjunto de asociaciones (`PublishedBy`) basados en el modelo conceptual mostrado anteriormente. BI en el `Books` conjunto de entidades representa una instancia del `Book` tipo de entidad en tiempo de ejecución. Del mismo modo, PJ representa una `Publisher` instancia en el `Publishers` conjunto de entidades. BiPj representa una instancia de la `PublishedBy` asociación en el `PublishedBy` conjunto de asociaciones.  
  
 ![Captura de pantalla que muestra un ejemplo de conjuntos.](./media/entity-set/sets-example-association.gif)  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El código CSDL siguiente define un contenedor de entidades con un conjunto de entidades para cada tipo de entidad del modelo conceptual mostrado anteriormente. Tenga en cuenta que el nombre y el tipo de entidad de cada conjunto de entidades se definen mediante atributos XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 Es posible definir varios conjuntos de entidades por tipo (MEST). El código CSDL siguiente define un contenedor de entidades con dos conjuntos de entidades para el tipo de entidad `Book`:  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a>Consulte también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
