---
title: tipo complejo
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: ef20de6a9e72d3123d745ef5501ecdb7fa63967d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203792"
---
# <a name="complex-type"></a><span data-ttu-id="aab50-102">tipo complejo</span><span class="sxs-lookup"><span data-stu-id="aab50-102">complex type</span></span>

<span data-ttu-id="aab50-103">Un *tipo complejo* es una plantilla para definir propiedades enriquecidas y estructuradas en [tipos de entidad](entity-type.md) o en otros tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="aab50-103">A *complex type* is a template for defining rich, structured properties on [entity types](entity-type.md) or on other complex types.</span></span> <span data-ttu-id="aab50-104">Cada plantilla contiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aab50-104">Each template contains the following:</span></span>  
  
- <span data-ttu-id="aab50-105">Un nombre único.</span><span class="sxs-lookup"><span data-stu-id="aab50-105">A unique name.</span></span> <span data-ttu-id="aab50-106">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="aab50-106">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="aab50-107">El nombre de un tipo complejo no puede coincidir con el nombre de un tipo de entidad dentro del mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="aab50-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
- <span data-ttu-id="aab50-108">Datos en forma de una o más [propiedades](property.md).</span><span class="sxs-lookup"><span data-stu-id="aab50-108">Data in the form of one or more [properties](property.md).</span></span> <span data-ttu-id="aab50-109">(Opcional).</span><span class="sxs-lookup"><span data-stu-id="aab50-109">(Optional.)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="aab50-110">Una propiedad de un tipo complejo puede ser otro tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="aab50-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="aab50-111">Un tipo complejo es similar a un tipo de entidad, ya que un tipo complejo puede llevar una carga de datos en forma de propiedades de tipo primitivo u otros tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="aab50-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="aab50-112">Sin embargo, existen algunas diferencias clave entre los tipos complejos y los tipos de entidad:</span><span class="sxs-lookup"><span data-stu-id="aab50-112">However, there are some key differences between complex types and entity types:</span></span>  
  
- <span data-ttu-id="aab50-113">Los tipos complejos no tienen identidades y, por consiguiente, no pueden existir de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="aab50-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="aab50-114">Los tipos complejos solo pueden existir como propiedades en tipos de entidad u otros tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="aab50-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
- <span data-ttu-id="aab50-115">Los tipos complejos no pueden participar en [asociaciones](association-type.md).</span><span class="sxs-lookup"><span data-stu-id="aab50-115">Complex types cannot participate in [associations](association-type.md).</span></span> <span data-ttu-id="aab50-116">Ninguno de los extremos de una asociación puede ser un tipo complejo y, por lo tanto, [las propiedades de navegación](navigation-property.md) no se pueden definir en tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="aab50-116">Neither end of an association can be a complex type, and therefore [navigation properties](navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aab50-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aab50-117">Example</span></span>  

 <span data-ttu-id="aab50-118">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="aab50-118">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="aab50-119">El código CSDL siguiente define un tipo complejo, Address, con las propiedades de tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="aab50-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="aab50-120">Para definir el tipo complejo `Address` (arriba) como una propiedad en un tipo de entidad, debe declarar el tipo de propiedad en la definición del tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="aab50-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="aab50-121">El código CSDL siguiente declara la propiedad `Address` como un tipo complejo en un tipo de entidad (Publisher):</span><span class="sxs-lookup"><span data-stu-id="aab50-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="aab50-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aab50-122">See also</span></span>

- [<span data-ttu-id="aab50-123">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="aab50-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="aab50-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="aab50-124">Entity Data Model</span></span>](entity-data-model.md)
