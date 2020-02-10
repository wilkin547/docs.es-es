---
title: Propiedad de navegación
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: eaf22ad4dd24b4bf046f14ccabd435a9ecd1776f
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094389"
---
# <a name="navigation-property"></a><span data-ttu-id="15643-102">Propiedad de navegación</span><span class="sxs-lookup"><span data-stu-id="15643-102">Navigation property</span></span>

<span data-ttu-id="15643-103">Una *propiedad de navegación* es una propiedad opcional en [un tipo de entidad](entity-type.md) que permite la navegación desde un [extremo](association-end.md) de una [Asociación](association-type.md) al otro extremo.</span><span class="sxs-lookup"><span data-stu-id="15643-103">A *navigation property* is an optional property on an [entity type](entity-type.md) that allows for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="15643-104">A diferencia de otras [propiedades](property.md), las propiedades de navegación no contienen datos.</span><span class="sxs-lookup"><span data-stu-id="15643-104">Unlike other [properties](property.md), navigation properties do not carry data.</span></span>

<span data-ttu-id="15643-105">Una definición de propiedad de desplazamiento incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15643-105">A navigation property definition includes the following:</span></span>

- <span data-ttu-id="15643-106">Un nombre.</span><span class="sxs-lookup"><span data-stu-id="15643-106">A name.</span></span> <span data-ttu-id="15643-107">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="15643-107">(Required)</span></span>

- <span data-ttu-id="15643-108">La asociación que navega.</span><span class="sxs-lookup"><span data-stu-id="15643-108">The association that it navigates.</span></span> <span data-ttu-id="15643-109">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="15643-109">(Required)</span></span>

- <span data-ttu-id="15643-110">Los extremos de la asociación que navega.</span><span class="sxs-lookup"><span data-stu-id="15643-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="15643-111">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="15643-111">(Required)</span></span>

<span data-ttu-id="15643-112">Las propiedades de navegación son opcionales en ambos tipos de entidad de los extremos de una asociación.</span><span class="sxs-lookup"><span data-stu-id="15643-112">Navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="15643-113">Si define una propiedad de navegación en un tipo de entidad del extremo de una asociación, no tiene que definir una propiedad de navegación en el tipo de entidad del otro extremo de la asociación.</span><span class="sxs-lookup"><span data-stu-id="15643-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>

<span data-ttu-id="15643-114">El tipo de datos de una propiedad de navegación viene determinado por la [multiplicidad](association-end-multiplicity.md) de su [extremo](association-end.md)de la Asociación remota.</span><span class="sxs-lookup"><span data-stu-id="15643-114">The data type of a navigation property is determined by the [multiplicity](association-end-multiplicity.md) of its remote [association end](association-end.md).</span></span> <span data-ttu-id="15643-115">Por ejemplo, supongamos que una propiedad de navegación, `OrdersNavProp`, existe en un tipo de entidad `Customer` y navega a una asociación uno a varios entre `Customer` y `Order`.</span><span class="sxs-lookup"><span data-stu-id="15643-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="15643-116">Dado que el extremo remoto de la Asociación para la propiedad de navegación tiene la multiplicidad de muchos (\*), su tipo de datos es una colección (de `Order`).</span><span class="sxs-lookup"><span data-stu-id="15643-116">Because the remote association end for the navigation property has multiplicity of many (\*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="15643-117">De igual forma, si una propiedad de navegación, `CustomerNavProp`, existe en el tipo de entidad `Order`, su tipo de datos sería `Customer`, porque la multiplicidad del extremo remoto es uno (1).</span><span class="sxs-lookup"><span data-stu-id="15643-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>

## <a name="example"></a><span data-ttu-id="15643-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15643-118">Example</span></span>

<span data-ttu-id="15643-119">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="15643-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="15643-120">Las propiedades de navegación `Publisher` y `Authors` se definen en el tipo de entidad Book.</span><span class="sxs-lookup"><span data-stu-id="15643-120">The navigation properties `Publisher` and `Authors` are defined on the Book entity type.</span></span> <span data-ttu-id="15643-121">La propiedad de navegación `Books` se define en el tipo de entidad Publisher y el tipo de entidad `Author`.</span><span class="sxs-lookup"><span data-stu-id="15643-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>

![Diagrama que muestra un modelo conceptual con tres tipos de entidad.](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

<span data-ttu-id="15643-123">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="15643-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="15643-124">El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="15643-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

<span data-ttu-id="15643-125">Los atributos XML se utilizan para comunicar la información necesaria para definir una propiedad de navegación: el atributo `Name` contiene el nombre de la propiedad, `Relationship` contiene el nombre de la asociación a la que navega y `FromRole` y `ToRole` contienen los extremos de la asociación.</span><span class="sxs-lookup"><span data-stu-id="15643-125">XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>

## <a name="see-also"></a><span data-ttu-id="15643-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15643-126">See also</span></span>

- [<span data-ttu-id="15643-127">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="15643-127">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="15643-128">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="15643-128">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="15643-129">Relaciones, propiedades de navegación y claves externas</span><span class="sxs-lookup"><span data-stu-id="15643-129">Relationships, navigation properties, and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)
