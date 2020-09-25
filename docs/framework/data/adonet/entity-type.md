---
title: tipo de entidad
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3f99667a06d8aa439232802d4909290dfe9db97c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194783"
---
# <a name="entity-type"></a><span data-ttu-id="1be08-102">tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="1be08-102">entity type</span></span>

<span data-ttu-id="1be08-103">El *tipo de entidad* es el bloque de creación fundamental para describir la estructura de los datos con el Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="1be08-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="1be08-104">En un modelo conceptual, un tipo de entidad representa la estructura de conceptos de nivel superior, como clientes o pedidos.</span><span class="sxs-lookup"><span data-stu-id="1be08-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="1be08-105">Un tipo de entidad es una plantilla para las instancias de tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="1be08-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="1be08-106">Cada plantilla contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="1be08-106">Each template contains the following information:</span></span>  
  
- <span data-ttu-id="1be08-107">Un nombre único.</span><span class="sxs-lookup"><span data-stu-id="1be08-107">A unique name.</span></span> <span data-ttu-id="1be08-108">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="1be08-108">(Required.)</span></span>  
  
- <span data-ttu-id="1be08-109">Una [clave de entidad](entity-key.md) definida por una o más propiedades.</span><span class="sxs-lookup"><span data-stu-id="1be08-109">An [entity key](entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="1be08-110">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="1be08-110">(Required.)</span></span>  
  
- <span data-ttu-id="1be08-111">Datos en forma de [propiedades](property.md).</span><span class="sxs-lookup"><span data-stu-id="1be08-111">Data in the form of [properties](property.md).</span></span> <span data-ttu-id="1be08-112">(Opcional).</span><span class="sxs-lookup"><span data-stu-id="1be08-112">(Optional.)</span></span>  
  
- <span data-ttu-id="1be08-113">[Propiedades de navegación](navigation-property.md) que permiten la navegación desde un [extremo](association-end.md) de una [Asociación](association-type.md) al otro extremo.</span><span class="sxs-lookup"><span data-stu-id="1be08-113">[Navigation properties](navigation-property.md) that allow for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="1be08-114">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="1be08-114">(Optional)</span></span>  
  
 <span data-ttu-id="1be08-115">En una aplicación, una instancia de un tipo de entidad representa un objeto específico (como un cliente o un pedido concreto).</span><span class="sxs-lookup"><span data-stu-id="1be08-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="1be08-116">Cada instancia de un tipo de entidad debe tener una [clave de entidad](entity-key.md) única dentro de un [conjunto de entidades](entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="1be08-116">Each instance of an entity type must have a unique [entity key](entity-key.md) within an [entity set](entity-set.md).</span></span>  
  
 <span data-ttu-id="1be08-117">Dos instancias de tipo de entidad se consideran iguales solo si son del mismo tipo y los valores de sus claves de entidad son idénticos.</span><span class="sxs-lookup"><span data-stu-id="1be08-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1be08-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1be08-118">Example</span></span>  

 <span data-ttu-id="1be08-119">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidad: `Book`, `Publisher` y `Author`:</span><span class="sxs-lookup"><span data-stu-id="1be08-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="1be08-121">Tenga en cuenta que las propiedades de cada tipo de entidad que constituyen su clave de entidad se denotan con "(Key)".</span><span class="sxs-lookup"><span data-stu-id="1be08-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="1be08-122">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="1be08-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="1be08-123">El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="1be08-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="1be08-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1be08-124">See also</span></span>

- [<span data-ttu-id="1be08-125">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="1be08-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="1be08-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="1be08-126">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="1be08-127">agrupa</span><span class="sxs-lookup"><span data-stu-id="1be08-127">facet</span></span>](facet.md)
