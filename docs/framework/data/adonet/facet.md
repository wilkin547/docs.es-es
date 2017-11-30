---
title: facet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e72ecd610951a42ceb5c3aa581bf70f255e5e2f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="facet"></a><span data-ttu-id="22411-102">facet</span><span class="sxs-lookup"><span data-stu-id="22411-102">facet</span></span>
<span data-ttu-id="22411-103">A *faceta* se usa para agregar detalles a una definición de propiedad de tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="22411-103">A *facet* is used to add detail to a primitive type property definition.</span></span> <span data-ttu-id="22411-104">A [propiedad](../../../../docs/framework/data/adonet/property.md) definición contiene información sobre el tipo de propiedad, pero a menudo es necesario más detalle.</span><span class="sxs-lookup"><span data-stu-id="22411-104">A [property](../../../../docs/framework/data/adonet/property.md) definition contains information about the property type, but often more detail is necessary.</span></span> <span data-ttu-id="22411-105">Por ejemplo, un tipo de entidad en un modelo conceptual podría tener una propiedad de tipo `String` cuyo valor no se puede establecer en NULL.</span><span class="sxs-lookup"><span data-stu-id="22411-105">For example, an entity type in a conceptual model might have a property of type `String` whose value cannot be set to null.</span></span> <span data-ttu-id="22411-106">Las facetas permiten especificar este nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="22411-106">Facets allow you to specify this level of detail.</span></span>  
  
 <span data-ttu-id="22411-107">En la siguiente tabla se describen las facetas que se admiten en EDM.</span><span class="sxs-lookup"><span data-stu-id="22411-107">The table below describes the facets that are supported in the EDM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22411-108">El entorno de tiempo de ejecución que utiliza una implementación de EDM determina los valores exactos y los comportamientos de las facetas.</span><span class="sxs-lookup"><span data-stu-id="22411-108">The exact values and behaviors of facets are determined by the run-time environment that uses an EDM implementation.</span></span>  
  
|<span data-ttu-id="22411-109">Faceta</span><span class="sxs-lookup"><span data-stu-id="22411-109">Facet</span></span>|<span data-ttu-id="22411-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="22411-110">Description</span></span>|<span data-ttu-id="22411-111">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="22411-111">Applies to</span></span>|  
|-----------|-----------------|----------------|  
|`Collation`|<span data-ttu-id="22411-112">Especifica la secuencia de intercalación (o secuencia de orden) que se va a usar cuando se realicen las operaciones de comparación y ordenación sobre los valores de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="22411-112">Specifies the collating sequence (or sorting sequence) to be used when performing comparison and ordering operations on values of the property.</span></span>|`String`|  
|`ConcurrencyMode`|<span data-ttu-id="22411-113">Indica que el valor de propiedad se debería utilizar para las comprobaciones de la simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="22411-113">Indicates that the value of the property should be used for optimistic concurrency checks.</span></span>|<span data-ttu-id="22411-114">Todas las propiedades de tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="22411-114">All primitive type properties</span></span>|  
|`Default`|<span data-ttu-id="22411-115">Especifica el valor predeterminado de la propiedad si no se proporciona ningún valor al crear las instancias.</span><span class="sxs-lookup"><span data-stu-id="22411-115">Specifies the default value of the property if no value is supplied upon instantiation.</span></span>|<span data-ttu-id="22411-116">Todas las propiedades de tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="22411-116">All primitive type properties</span></span>|  
|`FixedLength`|<span data-ttu-id="22411-117">Especifica si la longitud del valor de propiedad puede variar.</span><span class="sxs-lookup"><span data-stu-id="22411-117">Specifies whether the length of the property value can vary.</span></span>|<span data-ttu-id="22411-118">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="22411-118">`Binary`, `String`</span></span>|  
|`MaxLength`|<span data-ttu-id="22411-119">Especifica la longitud máxima del valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="22411-119">Specifies the maximum length of the property value.</span></span>|<span data-ttu-id="22411-120">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="22411-120">`Binary`, `String`</span></span>|  
|`Nullable`|<span data-ttu-id="22411-121">Especifica si la propiedad puede tener un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="22411-121">Specifies whether the property can have a null value.</span></span>|<span data-ttu-id="22411-122">Todas las propiedades de tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="22411-122">All primitive type properties</span></span>|  
|`Precision`|<span data-ttu-id="22411-123">Para las propiedades de tipo `Decimal`, especifica el número de dígitos que puede tener un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="22411-123">For properties of type `Decimal`, specifies the number of digits a property value can have.</span></span> <span data-ttu-id="22411-124">Para las propiedades de tipo `Time`, `DateTime` y `DateTimeOffset`, especifica el número de dígitos para la parte fraccionaria de los segundos del valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="22411-124">For properties of type `Time`, `DateTime`, and `DateTimeOffset`, specifies the number of digits for the fractional part of seconds of the property value.</span></span>|<span data-ttu-id="22411-125">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span><span class="sxs-lookup"><span data-stu-id="22411-125">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span></span>|  
|`Scale`|<span data-ttu-id="22411-126">Especifica el número de dígitos que puede haber a la derecha del separador decimal para el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="22411-126">Specifies the number of digits to the right of the decimal point for the property value.</span></span>|<span data-ttu-id="22411-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="22411-127">Decimal</span></span>|  
|`Unicode`|<span data-ttu-id="22411-128">Indica si el valor de propiedad está almacenado como Unicode.</span><span class="sxs-lookup"><span data-stu-id="22411-128">Indicates whether the property value is stored as Unicode.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="22411-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22411-129">Example</span></span>  
 <span data-ttu-id="22411-130">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="22411-130">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="22411-131">En el ejemplo siguiente CSDL, se define un tipo de entidad `Book`.</span><span class="sxs-lookup"><span data-stu-id="22411-131">The following CSDL defines a `Book` entity type.</span></span> <span data-ttu-id="22411-132">Observe que las facetas se implementan como atributos XML.</span><span class="sxs-lookup"><span data-stu-id="22411-132">Note that facets are implemented as XML attributes.</span></span> <span data-ttu-id="22411-133">Los valores de faceta indican que ninguna propiedad puede estar establecida en NULL, y que los valores `Scale` y `Precision` de la propiedad `Revision` están establecidos ambos en 29.</span><span class="sxs-lookup"><span data-stu-id="22411-133">The facet values indicate that no property can be set to null, and that the `Scale` and `Precision` of the `Revision` property are each set to 29.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="22411-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="22411-134">See Also</span></span>  
 [<span data-ttu-id="22411-135">Conceptos básicos de modelo de datos de entidad</span><span class="sxs-lookup"><span data-stu-id="22411-135">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="22411-136">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="22411-136">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
