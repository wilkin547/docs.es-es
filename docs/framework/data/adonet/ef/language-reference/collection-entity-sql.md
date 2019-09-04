---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 0e611add4ce3f20e42bb01b0bf0392bbe81ec548
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251195"
---
# <a name="collection-entity-sql"></a><span data-ttu-id="00249-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="00249-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="00249-103">La palabra clave COLLECTION solo se usa en la definición de una función inline.</span><span class="sxs-lookup"><span data-stu-id="00249-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="00249-104">Las funciones de colección son funciones que operan en una colección de valores y generan un resultado escalar.</span><span class="sxs-lookup"><span data-stu-id="00249-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00249-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00249-105">Syntax</span></span>  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a><span data-ttu-id="00249-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="00249-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="00249-107">Una expresión que devuelve una colección de tipos, filas o referencias compatibles.</span><span class="sxs-lookup"><span data-stu-id="00249-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00249-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00249-108">Remarks</span></span>  
 <span data-ttu-id="00249-109">Para obtener más información sobre la palabra clave COLLECTION, vea [Type Definitions](type-definitions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="00249-109">For more information about the COLLECTION keyword, see [Type Definitions](type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00249-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00249-110">Example</span></span>  
 <span data-ttu-id="00249-111">En el ejemplo siguiente se muestra cómo usar la palabra clave COLLECTION para declarar una colección de decimales como un argumento para una función inline de consulta.</span><span class="sxs-lookup"><span data-stu-id="00249-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="00249-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="00249-112">See also</span></span>

- [<span data-ttu-id="00249-113">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="00249-113">Entity SQL Reference</span></span>](entity-sql-reference.md)
