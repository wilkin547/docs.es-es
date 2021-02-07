---
description: 'Más información acerca de: tipo de entidad'
title: tipo de entidad
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: fb801ca8565fce01466f30bddc8c14c39af568c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724367"
---
# <a name="entity-type"></a><span data-ttu-id="a16a0-103">tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="a16a0-103">entity type</span></span>

<span data-ttu-id="a16a0-104">El *tipo de entidad* es el bloque de creación fundamental para describir la estructura de los datos con el Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="a16a0-104">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="a16a0-105">En un modelo conceptual, un tipo de entidad representa la estructura de conceptos de nivel superior, como clientes o pedidos.</span><span class="sxs-lookup"><span data-stu-id="a16a0-105">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="a16a0-106">Un tipo de entidad es una plantilla para las instancias de tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="a16a0-106">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="a16a0-107">Cada plantilla contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="a16a0-107">Each template contains the following information:</span></span>  
  
- <span data-ttu-id="a16a0-108">Un nombre único.</span><span class="sxs-lookup"><span data-stu-id="a16a0-108">A unique name.</span></span> <span data-ttu-id="a16a0-109">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="a16a0-109">(Required.)</span></span>  
  
- <span data-ttu-id="a16a0-110">Una [clave de entidad](entity-key.md) definida por una o más propiedades.</span><span class="sxs-lookup"><span data-stu-id="a16a0-110">An [entity key](entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="a16a0-111">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="a16a0-111">(Required.)</span></span>  
  
- <span data-ttu-id="a16a0-112">Datos en forma de [propiedades](property.md).</span><span class="sxs-lookup"><span data-stu-id="a16a0-112">Data in the form of [properties](property.md).</span></span> <span data-ttu-id="a16a0-113">(Opcional).</span><span class="sxs-lookup"><span data-stu-id="a16a0-113">(Optional.)</span></span>  
  
- <span data-ttu-id="a16a0-114">[Propiedades de navegación](navigation-property.md) que permiten la navegación desde un [extremo](association-end.md) de una [Asociación](association-type.md) al otro extremo.</span><span class="sxs-lookup"><span data-stu-id="a16a0-114">[Navigation properties](navigation-property.md) that allow for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="a16a0-115">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="a16a0-115">(Optional)</span></span>  
  
 <span data-ttu-id="a16a0-116">En una aplicación, una instancia de un tipo de entidad representa un objeto específico (como un cliente o un pedido concreto).</span><span class="sxs-lookup"><span data-stu-id="a16a0-116">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="a16a0-117">Cada instancia de un tipo de entidad debe tener una [clave de entidad](entity-key.md) única dentro de un [conjunto de entidades](entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="a16a0-117">Each instance of an entity type must have a unique [entity key](entity-key.md) within an [entity set](entity-set.md).</span></span>  
  
 <span data-ttu-id="a16a0-118">Dos instancias de tipo de entidad se consideran iguales solo si son del mismo tipo y los valores de sus claves de entidad son idénticos.</span><span class="sxs-lookup"><span data-stu-id="a16a0-118">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a16a0-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a16a0-119">Example</span></span>  

 <span data-ttu-id="a16a0-120">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidad: `Book`, `Publisher` y `Author`:</span><span class="sxs-lookup"><span data-stu-id="a16a0-120">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="a16a0-122">Tenga en cuenta que las propiedades de cada tipo de entidad que constituyen su clave de entidad se denotan con "(Key)".</span><span class="sxs-lookup"><span data-stu-id="a16a0-122">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="a16a0-123">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="a16a0-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="a16a0-124">El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="a16a0-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="a16a0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a16a0-125">See also</span></span>

- [<span data-ttu-id="a16a0-126">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="a16a0-126">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="a16a0-127">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="a16a0-127">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="a16a0-128">agrupa</span><span class="sxs-lookup"><span data-stu-id="a16a0-128">facet</span></span>](facet.md)
