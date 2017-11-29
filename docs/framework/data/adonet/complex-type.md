---
title: tipo complejo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 389a3be7342005e424c89ff4e430b4a257f2da5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="complex-type"></a><span data-ttu-id="a1db0-102">tipo complejo</span><span class="sxs-lookup"><span data-stu-id="a1db0-102">complex type</span></span>
<span data-ttu-id="a1db0-103">A *tipo complejo* es una plantilla para definir propiedades enriquecidas y estructuradas para [tipos de entidad](../../../../docs/framework/data/adonet/entity-type.md) u otros tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="a1db0-103">A *complex type* is a template for defining rich, structured properties on [entity types](../../../../docs/framework/data/adonet/entity-type.md) or on other complex types.</span></span> <span data-ttu-id="a1db0-104">Cada plantilla contiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1db0-104">Each template contains the following:</span></span>  
  
-   <span data-ttu-id="a1db0-105">Un nombre único.</span><span class="sxs-lookup"><span data-stu-id="a1db0-105">A unique name.</span></span> <span data-ttu-id="a1db0-106">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="a1db0-106">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1db0-107">El nombre de un tipo complejo no puede coincidir con el nombre de un tipo de entidad dentro del mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a1db0-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
-   <span data-ttu-id="a1db0-108">Datos en forma de uno o varios [propiedades](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="a1db0-108">Data in the form of one or more [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="a1db0-109">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="a1db0-109">(Optional.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1db0-110">Una propiedad de un tipo complejo puede ser otro tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="a1db0-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="a1db0-111">Un tipo complejo es similar a un tipo de entidad, ya que un tipo complejo puede llevar una carga de datos en forma de propiedades de tipo primitivo u otros tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="a1db0-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="a1db0-112">Sin embargo, existen algunas diferencias clave entre los tipos complejos y los tipos de entidad:</span><span class="sxs-lookup"><span data-stu-id="a1db0-112">However, there are some key differences between complex types and entity types:</span></span>  
  
-   <span data-ttu-id="a1db0-113">Los tipos complejos no tienen identidades y, por consiguiente, no pueden existir de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="a1db0-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="a1db0-114">Los tipos complejos solo pueden existir como propiedades en tipos de entidad u otros tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="a1db0-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
-   <span data-ttu-id="a1db0-115">Tipos complejos no pueden participar en [asociaciones](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="a1db0-115">Complex types cannot participate in [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="a1db0-116">Los extremos de una asociación pueden ser un tipo complejo y, por tanto, [propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) no pueden definirse en tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="a1db0-116">Neither end of an association can be a complex type, and therefore [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1db0-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1db0-117">Example</span></span>  
 <span data-ttu-id="a1db0-118">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="a1db0-118">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="a1db0-119">El código CSDL siguiente define un tipo complejo, Address, con las propiedades de tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` y `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="a1db0-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="a1db0-120">Para definir el tipo complejo `Address` (arriba) como una propiedad en un tipo de entidad, debe declarar el tipo de propiedad en la definición del tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="a1db0-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="a1db0-121">El código CSDL siguiente declara la propiedad `Address` como un tipo complejo en un tipo de entidad (Publisher):</span><span class="sxs-lookup"><span data-stu-id="a1db0-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="a1db0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1db0-122">See Also</span></span>  
 [<span data-ttu-id="a1db0-123">Conceptos básicos de modelo de datos de entidad</span><span class="sxs-lookup"><span data-stu-id="a1db0-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="a1db0-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="a1db0-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
