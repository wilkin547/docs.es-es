---
description: 'Más información sobre: colección (Entity SQL)'
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 1269680b2a9009277e79337cfe4df154885b7c1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697054"
---
# <a name="collection-entity-sql"></a><span data-ttu-id="827d0-103">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="827d0-103">COLLECTION (Entity SQL)</span></span>

<span data-ttu-id="827d0-104">La palabra clave COLLECTION solo se usa en la definición de una función inline.</span><span class="sxs-lookup"><span data-stu-id="827d0-104">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="827d0-105">Las funciones de colección son funciones que operan en una colección de valores y generan un resultado escalar.</span><span class="sxs-lookup"><span data-stu-id="827d0-105">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="827d0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="827d0-106">Syntax</span></span>  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a><span data-ttu-id="827d0-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="827d0-107">Arguments</span></span>  

 `type_definition`  
 <span data-ttu-id="827d0-108">Una expresión que devuelve una colección de tipos, filas o referencias compatibles.</span><span class="sxs-lookup"><span data-stu-id="827d0-108">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="827d0-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="827d0-109">Remarks</span></span>  

 <span data-ttu-id="827d0-110">Para obtener más información sobre la palabra clave COLLECTION, vea [Type Definitions](type-definitions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="827d0-110">For more information about the COLLECTION keyword, see [Type Definitions](type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="827d0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="827d0-111">Example</span></span>  

 <span data-ttu-id="827d0-112">En el ejemplo siguiente se muestra cómo usar la palabra clave COLLECTION para declarar una colección de decimales como un argumento para una función inline de consulta.</span><span class="sxs-lookup"><span data-stu-id="827d0-112">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="827d0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="827d0-113">See also</span></span>

- [<span data-ttu-id="827d0-114">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="827d0-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
