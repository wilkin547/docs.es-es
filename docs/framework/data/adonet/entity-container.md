---
title: contenedor de entidades
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 58642c6cc794f931387ac7a76dd64d368957f14b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586955"
---
# <a name="entity-container"></a><span data-ttu-id="f5a3b-102">contenedor de entidades</span><span class="sxs-lookup"><span data-stu-id="f5a3b-102">entity container</span></span>
<span data-ttu-id="f5a3b-103">Un *contenedor de entidades* es una agrupación lógica de [conjuntos de entidades](../../../../docs/framework/data/adonet/entity-set.md), [conjuntos de asociaciones](../../../../docs/framework/data/adonet/association-set.md), y [importaciones de función](../../../../docs/framework/data/adonet/model-declared-function.md).</span><span class="sxs-lookup"><span data-stu-id="f5a3b-103">An *entity container* is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md), [association sets](../../../../docs/framework/data/adonet/association-set.md), and [function imports](../../../../docs/framework/data/adonet/model-declared-function.md).</span></span>  
  
 <span data-ttu-id="f5a3b-104">Un contenedor de entidades definido en un modelo conceptual debe cumplir las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5a3b-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
- <span data-ttu-id="f5a3b-105">Se debe definir al menos un contenedor de entidades en cada modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="f5a3b-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
- <span data-ttu-id="f5a3b-106">El contenedor de entidades debe tener un nombre único en cada modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="f5a3b-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="f5a3b-107">Un contenedor de entidades puede definir conjuntos de entidades o de asociaciones que usan tipos de entidad o asociaciones definidos en uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="f5a3b-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="f5a3b-108">Para obtener más información, consulte [Entity Data Model: Los espacios de nombres](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="f5a3b-108">For more information, see [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5a3b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5a3b-109">Example</span></span>  
 <span data-ttu-id="f5a3b-110">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="f5a3b-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="f5a3b-111">Para obtener más información, vea el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5a3b-111">See the next example for more information.</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/entity-container/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="f5a3b-113">Aunque el diagrama no proporciona información sobre el contenedor de entidades, el modelo conceptual debe definir un contenedor de entidades.</span><span class="sxs-lookup"><span data-stu-id="f5a3b-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="f5a3b-114">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un DSL denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="f5a3b-114">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="f5a3b-115">El código CSDL siguiente define un contenedor de entidades para el modelo conceptual mostrado en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="f5a3b-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="f5a3b-116">Tenga en cuenta que el nombre del contenedor de entidades se define en un atributo XML.</span><span class="sxs-lookup"><span data-stu-id="f5a3b-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="f5a3b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5a3b-117">See also</span></span>

- [<span data-ttu-id="f5a3b-118">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="f5a3b-118">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="f5a3b-119">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="f5a3b-119">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
