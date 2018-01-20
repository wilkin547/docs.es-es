---
title: "función declarada por el modelo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 37c6b04fbea69f62aaf7bc148ee04ace5a5a349c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="model-declared-function"></a><span data-ttu-id="5f301-102">función declarada por el modelo</span><span class="sxs-lookup"><span data-stu-id="5f301-102">model-declared function</span></span>
<span data-ttu-id="5f301-103">A *función declarada por modelo* es una función que se declara en un modelo conceptual, pero no está definida en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="5f301-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="5f301-104">La función se podría definir en el entorno de almacenamiento u hospedaje.</span><span class="sxs-lookup"><span data-stu-id="5f301-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="5f301-105">Por ejemplo, una función declarada por modelo se podría asignar a una función definida en una base de datos, exponiendo así la funcionalidad de servidor en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="5f301-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="5f301-106">La declaración de una función declarada por modelo contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="5f301-106">The declaration of a model-declared function contains the following information:</span></span>  
  
-   <span data-ttu-id="5f301-107">Nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="5f301-107">The name of the function.</span></span> <span data-ttu-id="5f301-108">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="5f301-108">(Required)</span></span>  
  
-   <span data-ttu-id="5f301-109">El tipo del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="5f301-109">The type of the return value.</span></span> <span data-ttu-id="5f301-110">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="5f301-110">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5f301-111">Si no se especifica ningún valor devuelto, el tipo de valor devuelto es void.</span><span class="sxs-lookup"><span data-stu-id="5f301-111">If no return value is specified, the return type is void.</span></span>  
  
-   <span data-ttu-id="5f301-112">Información de parámetro, incluidos el tipo y el nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="5f301-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="5f301-113">(Opcional)</span><span class="sxs-lookup"><span data-stu-id="5f301-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f301-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5f301-114">Example</span></span>  
 <span data-ttu-id="5f301-115">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="5f301-115">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="5f301-116">En CSDL, una implementación de una función declarada por modelo es un [importación de funciones](http://msdn.microsoft.com/library/125704ae-56c7-4233-80b7-389a10f3a65d).</span><span class="sxs-lookup"><span data-stu-id="5f301-116">In CSDL, one implementation of a model-declared function is a [function import](http://msdn.microsoft.com/library/125704ae-56c7-4233-80b7-389a10f3a65d).</span></span> <span data-ttu-id="5f301-117">El siguiente CSDL define un contenedor de la entidad con una definición de importación de función.</span><span class="sxs-lookup"><span data-stu-id="5f301-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="5f301-118">Tenga en cuenta que el tipo de valor devuelto es void porque no se especifica ningún tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="5f301-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="5f301-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f301-119">See Also</span></span>  
 [<span data-ttu-id="5f301-120">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="5f301-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="5f301-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="5f301-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
