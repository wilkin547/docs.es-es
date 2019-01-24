---
title: tipo de entidad
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3955de1873d80e85df713a557750e34e76efeb41
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502889"
---
# <a name="entity-type"></a><span data-ttu-id="2a425-102">tipo de entidad</span><span class="sxs-lookup"><span data-stu-id="2a425-102">entity type</span></span>
<span data-ttu-id="2a425-103">El *tipo de entidad* es el bloque de creación fundamental para describir la estructura de datos con Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="2a425-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="2a425-104">En un modelo conceptual, un tipo de entidad representa la estructura de conceptos de nivel superior, como clientes o pedidos.</span><span class="sxs-lookup"><span data-stu-id="2a425-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="2a425-105">Un tipo de entidad es una plantilla para las instancias de tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="2a425-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="2a425-106">Cada plantilla contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="2a425-106">Each template contains the following information:</span></span>  
  
-   <span data-ttu-id="2a425-107">Un nombre único.</span><span class="sxs-lookup"><span data-stu-id="2a425-107">A unique name.</span></span> <span data-ttu-id="2a425-108">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="2a425-108">(Required.)</span></span>  
  
-   <span data-ttu-id="2a425-109">Un [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) definido por una o varias propiedades.</span><span class="sxs-lookup"><span data-stu-id="2a425-109">An [entity key](../../../../docs/framework/data/adonet/entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="2a425-110">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="2a425-110">(Required.)</span></span>  
  
-   <span data-ttu-id="2a425-111">Datos en forma de [propiedades](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="2a425-111">Data in the form of [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="2a425-112">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="2a425-112">(Optional.)</span></span>  
  
-   <span data-ttu-id="2a425-113">[Las propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) que permiten la navegación de una [final](../../../../docs/framework/data/adonet/association-end.md) de un [asociación](../../../../docs/framework/data/adonet/association-type.md) al otro extremo.</span><span class="sxs-lookup"><span data-stu-id="2a425-113">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) that allow for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="2a425-114">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="2a425-114">(Optional)</span></span>  
  
 <span data-ttu-id="2a425-115">En una aplicación, una instancia de un tipo de entidad representa un objeto específico (como un cliente o un pedido concreto).</span><span class="sxs-lookup"><span data-stu-id="2a425-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="2a425-116">Cada instancia de un tipo de entidad debe tener un único [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) dentro de un [conjunto de entidades](../../../../docs/framework/data/adonet/entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="2a425-116">Each instance of an entity type must have a unique [entity key](../../../../docs/framework/data/adonet/entity-key.md) within an [entity set](../../../../docs/framework/data/adonet/entity-set.md).</span></span>  
  
 <span data-ttu-id="2a425-117">Dos instancias de tipo de entidad se consideran iguales solo si son del mismo tipo y los valores de sus claves de entidad son idénticos.</span><span class="sxs-lookup"><span data-stu-id="2a425-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a425-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a425-118">Example</span></span>  
 <span data-ttu-id="2a425-119">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidad: `Book`, `Publisher` y `Author`:</span><span class="sxs-lookup"><span data-stu-id="2a425-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 <span data-ttu-id="2a425-120">![Ejemplo de modelo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="2a425-120">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="2a425-121">Tenga en cuenta que las propiedades de cada tipo de entidad que constituyen su clave de entidad se denotan con "(Key)".</span><span class="sxs-lookup"><span data-stu-id="2a425-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="2a425-122">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="2a425-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="2a425-123">El siguiente CSDL define el tipo de entidad `Book` mostrado en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="2a425-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="2a425-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a425-124">See also</span></span>
- [<span data-ttu-id="2a425-125">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="2a425-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="2a425-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="2a425-126">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
- [<span data-ttu-id="2a425-127">facet</span><span class="sxs-lookup"><span data-stu-id="2a425-127">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)
