---
description: 'Más información sobre: función declarada por modelo'
title: función declarada por el modelo
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: c9a5cedb8c9706aa0d299635f60f762b92ca6d78
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786269"
---
# <a name="model-declared-function"></a><span data-ttu-id="fdc40-103">función declarada por el modelo</span><span class="sxs-lookup"><span data-stu-id="fdc40-103">model-declared function</span></span>

<span data-ttu-id="fdc40-104">Una *función declarada por el modelo* es una función que se declara en un modelo conceptual, pero que no está definida en ese modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="fdc40-104">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="fdc40-105">La función se podría definir en el entorno de almacenamiento u hospedaje.</span><span class="sxs-lookup"><span data-stu-id="fdc40-105">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="fdc40-106">Por ejemplo, una función declarada por modelo se podría asignar a una función definida en una base de datos, exponiendo así la funcionalidad de servidor en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="fdc40-106">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="fdc40-107">La declaración de una función declarada por modelo contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="fdc40-107">The declaration of a model-declared function contains the following information:</span></span>  
  
- <span data-ttu-id="fdc40-108">Nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="fdc40-108">The name of the function.</span></span> <span data-ttu-id="fdc40-109">(Requerido)</span><span class="sxs-lookup"><span data-stu-id="fdc40-109">(Required)</span></span>  
  
- <span data-ttu-id="fdc40-110">El tipo del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="fdc40-110">The type of the return value.</span></span> <span data-ttu-id="fdc40-111">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="fdc40-111">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fdc40-112">Si no se especifica ningún valor devuelto, el tipo de valor devuelto es void.</span><span class="sxs-lookup"><span data-stu-id="fdc40-112">If no return value is specified, the return type is void.</span></span>  
  
- <span data-ttu-id="fdc40-113">Información de parámetro, incluidos el tipo y el nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="fdc40-113">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="fdc40-114">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="fdc40-114">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdc40-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdc40-115">Example</span></span>  

 <span data-ttu-id="fdc40-116">El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="fdc40-116">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="fdc40-117">En CSDL, una implementación de una función declarada por modelo es una importación de función (mediante el [elemento FunctionImport](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span><span class="sxs-lookup"><span data-stu-id="fdc40-117">In CSDL, one implementation of a model-declared function is a function import (using the [FunctionImport element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span></span> <span data-ttu-id="fdc40-118">El siguiente CSDL define un contenedor de la entidad con una definición de importación de función.</span><span class="sxs-lookup"><span data-stu-id="fdc40-118">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="fdc40-119">Tenga en cuenta que el tipo de valor devuelto es void porque no se especifica ningún tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="fdc40-119">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="fdc40-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdc40-120">See also</span></span>

- [<span data-ttu-id="fdc40-121">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="fdc40-121">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="fdc40-122">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="fdc40-122">Entity Data Model</span></span>](entity-data-model.md)
