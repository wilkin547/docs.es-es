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
# <a name="entity-container"></a><span data-ttu-id="76364-102">contenedor de entidades</span><span class="sxs-lookup"><span data-stu-id="76364-102">entity container</span></span>
<span data-ttu-id="76364-103">Un *contenedor de entidades* es una agrupación lógica [de conjuntos de entidades](entity-set.md), conjuntos de [asociaciones](association-set.md)e [importaciones de funciones](model-declared-function.md).</span><span class="sxs-lookup"><span data-stu-id="76364-103">An *entity container* is a logical grouping of [entity sets](entity-set.md), [association sets](association-set.md), and [function imports](model-declared-function.md).</span></span>  
  
 <span data-ttu-id="76364-104">Un contenedor de entidades definido en un modelo conceptual debe cumplir las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="76364-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
- <span data-ttu-id="76364-105">Se debe definir al menos un contenedor de entidades en cada modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="76364-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
- <span data-ttu-id="76364-106">El contenedor de entidades debe tener un nombre único en cada modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="76364-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="76364-107">Un contenedor de entidades puede definir conjuntos de entidades o de asociaciones que usan tipos de entidad o asociaciones definidos en uno o varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="76364-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="76364-108">Para obtener más información, [vea Entity Data Model: Espacios de nombres.](entity-data-model-namespaces.md)</span><span class="sxs-lookup"><span data-stu-id="76364-108">For more information, see [Entity Data Model: Namespaces](entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76364-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76364-109">Example</span></span>  
 <span data-ttu-id="76364-110">El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="76364-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="76364-111">Para obtener más información, vea el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="76364-111">See the next example for more information.</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/entity-container/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="76364-113">Aunque el diagrama no proporciona información sobre el contenedor de entidades, el modelo conceptual debe definir un contenedor de entidades.</span><span class="sxs-lookup"><span data-stu-id="76364-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="76364-114">El [Entity Framework ADO.net](./ef/index.md) usa un DSL denominado lenguaje de definición de esquemas conceptuales ([CSDL](./ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="76364-114">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="76364-115">El código CSDL siguiente define un contenedor de entidades para el modelo conceptual mostrado en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="76364-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="76364-116">Tenga en cuenta que el nombre del contenedor de entidades se define en un atributo XML.</span><span class="sxs-lookup"><span data-stu-id="76364-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="76364-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="76364-117">See also</span></span>

- [<span data-ttu-id="76364-118">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="76364-118">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="76364-119">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="76364-119">Entity Data Model</span></span>](entity-data-model.md)
