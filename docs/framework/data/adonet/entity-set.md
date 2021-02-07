---
description: 'Más información acerca de: conjunto de entidades'
title: conjunto de entidades
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: 4881be280e1da2d53db6fc9f526289cdcd82ee07
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724432"
---
# <a name="entity-set"></a><span data-ttu-id="d2068-103">conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="d2068-103">entity set</span></span>

<span data-ttu-id="d2068-104">Un *conjunto de entidades* es un contenedor lógico para las instancias de un [tipo de entidad](entity-type.md) y las instancias de cualquier tipo derivado de ese tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="d2068-104">An *entity set* is a logical container for instances of an [entity type](entity-type.md) and instances of any type derived from that entity type.</span></span> <span data-ttu-id="d2068-105">(Para obtener información sobre los tipos derivados, vea [Entity Data Model: herencia](entity-data-model-inheritance.md)). La relación entre un tipo de entidad y un conjunto de entidades es análoga a la relación entre una fila y una tabla en una base de datos relacional: como una fila, un tipo de entidad describe la estructura de datos y, como una tabla, un conjunto de entidades contiene instancias de una estructura determinada.</span><span class="sxs-lookup"><span data-stu-id="d2068-105">(For information about derived types, see [Entity Data Model: Inheritance](entity-data-model-inheritance.md).) The relationship between an entity type and an entity set is analogous to the relationship between a row and a table in a relational database: Like a row, an entity type describes data structure, and, like a table, an entity set contains instances of a given structure.</span></span> <span data-ttu-id="d2068-106">Un conjunto de entidades no es una construcción de modelado de datos, ya que no describe la estructura de los datos.</span><span class="sxs-lookup"><span data-stu-id="d2068-106">An entity set is not a data modeling construct; it does not describe the structure of data.</span></span> <span data-ttu-id="d2068-107">En su lugar, un conjunto de entidades proporciona una construcción para que un entorno de hospedaje o de almacenamiento (como Common Language Runtime o una base de datos de SQL Server) agrupe las instancias del tipo de entidad y se puedan asignar a un almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="d2068-107">Instead, an entity set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group entity type instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="d2068-108">Un conjunto de entidades se define dentro de un [contenedor de entidades](entity-container.md), que es una agrupación lógica de conjuntos de entidades y [conjuntos de asociaciones](association-set.md).</span><span class="sxs-lookup"><span data-stu-id="d2068-108">An entity set is defined within an [entity container](entity-container.md), which is a logical grouping of entity sets and [association sets](association-set.md).</span></span>  
  
 <span data-ttu-id="d2068-109">Para que una instancia de tipo de entidad exista en un conjunto de entidades, deben cumplirse las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2068-109">For an entity type instance to exist in an entity set, the following must be true:</span></span>  
  
- <span data-ttu-id="d2068-110">El tipo de la instancia puede ser el mismo que el tipo de entidad en el que se basa el conjunto de entidades, o un subtipo del tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="d2068-110">The type of the instance is either the same as the entity type on which the entity set is based, or the type of the instance is a subtype of the entity type.</span></span>  
  
- <span data-ttu-id="d2068-111">La [clave de entidad](entity-key.md) para la instancia es única en el conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="d2068-111">The [entity key](entity-key.md) for the instance is unique within the entity set.</span></span>  
  
- <span data-ttu-id="d2068-112">La instancia no existe en ningún otro conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="d2068-112">The instance does not exist in any other entity set.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d2068-113">Se pueden definir varios conjuntos de entidades usando el mismo tipo de entidad, pero una instancia de un tipo de entidad determinado solo puede existir en un conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="d2068-113">Multiple entity sets can be defined using the same entity type, but an instance of a given entity type can only exist in one entity set.</span></span>  
  
 <span data-ttu-id="d2068-114">No es necesario definir un conjunto de entidades para cada tipo de entidad de un modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="d2068-114">You do not have to define an entity set for each entity type in a conceptual model.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2068-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2068-115">Example</span></span>  

 <span data-ttu-id="d2068-116">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="d2068-116">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/entity-set/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="d2068-118">El diagrama siguiente muestra dos conjuntos de entidades (`Books` y `Publishers`) y un conjunto de asociaciones (`PublishedBy`) basados en el modelo conceptual mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d2068-118">The following diagram shows two entity sets (`Books` and `Publishers`) and an association set (`PublishedBy`) based on the conceptual model shown above.</span></span> <span data-ttu-id="d2068-119">BI en el `Books` conjunto de entidades representa una instancia del `Book` tipo de entidad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d2068-119">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="d2068-120">Del mismo modo, PJ representa una `Publisher` instancia en el `Publishers` conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="d2068-120">Similarly, Pj represent a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="d2068-121">BiPj representa una instancia de la `PublishedBy` asociación en el `PublishedBy` conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="d2068-121">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Captura de pantalla que muestra un ejemplo de conjuntos.](./media/entity-set/sets-example-association.gif)  
  
 <span data-ttu-id="d2068-123">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="d2068-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="d2068-124">El código CSDL siguiente define un contenedor de entidades con un conjunto de entidades para cada tipo de entidad del modelo conceptual mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d2068-124">The following CSDL defines an entity container with one entity set for each entity type in the conceptual model shown above.</span></span> <span data-ttu-id="d2068-125">Tenga en cuenta que el nombre y el tipo de entidad de cada conjunto de entidades se definen mediante atributos XML.</span><span class="sxs-lookup"><span data-stu-id="d2068-125">Note that the name and entity type for each entity set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="d2068-126">Es posible definir varios conjuntos de entidades por tipo (MEST).</span><span class="sxs-lookup"><span data-stu-id="d2068-126">It is possible to define multiple entity sets per type (MEST).</span></span> <span data-ttu-id="d2068-127">El código CSDL siguiente define un contenedor de entidades con dos conjuntos de entidades para el tipo de entidad `Book`:</span><span class="sxs-lookup"><span data-stu-id="d2068-127">The following CSDL defines an entity container with two entity sets for the `Book` entity type:</span></span>  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a><span data-ttu-id="d2068-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2068-128">See also</span></span>

- [<span data-ttu-id="d2068-129">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d2068-129">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="d2068-130">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d2068-130">Entity Data Model</span></span>](entity-data-model.md)
