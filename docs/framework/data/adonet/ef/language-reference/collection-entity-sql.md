---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 5a1af1aab8a084b19e48fbdbb159d7ddd8a8dd7c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039901"
---
# <a name="collection-entity-sql"></a><span data-ttu-id="dfe1e-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dfe1e-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="dfe1e-103">La palabra clave COLLECTION solo se usa en la definición de una función inline.</span><span class="sxs-lookup"><span data-stu-id="dfe1e-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="dfe1e-104">Las funciones de colección son funciones que operan en una colección de valores y generan un resultado escalar.</span><span class="sxs-lookup"><span data-stu-id="dfe1e-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe1e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfe1e-105">Syntax</span></span>  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a><span data-ttu-id="dfe1e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dfe1e-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="dfe1e-107">Una expresión que devuelve una colección de tipos, filas o referencias compatibles.</span><span class="sxs-lookup"><span data-stu-id="dfe1e-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfe1e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dfe1e-108">Remarks</span></span>  
 <span data-ttu-id="dfe1e-109">Para obtener más información sobre la palabra clave COLLECTION, vea [Type Definitions](type-definitions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="dfe1e-109">For more information about the COLLECTION keyword, see [Type Definitions](type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfe1e-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfe1e-110">Example</span></span>  
 <span data-ttu-id="dfe1e-111">En el ejemplo siguiente se muestra cómo usar la palabra clave COLLECTION para declarar una colección de decimales como un argumento para una función inline de consulta.</span><span class="sxs-lookup"><span data-stu-id="dfe1e-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="dfe1e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfe1e-112">See also</span></span>

- [<span data-ttu-id="dfe1e-113">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="dfe1e-113">Entity SQL Reference</span></span>](entity-sql-reference.md)
