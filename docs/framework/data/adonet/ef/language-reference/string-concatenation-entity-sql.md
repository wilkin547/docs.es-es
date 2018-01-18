---
title: "+ (Concatenación de cadenas) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6019f6025b3a3996c9b86a6c9e61a3dd345c1b12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="039d1-102">+ (Concatenación de cadenas) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="039d1-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="039d1-103">Concatena dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="039d1-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="039d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="039d1-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="039d1-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="039d1-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="039d1-106">Cualquier expresión válida de los tipos de datos EDM.String.</span><span class="sxs-lookup"><span data-stu-id="039d1-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="039d1-107">Ambas expresiones deben ser del mismo tipo de datos o una se debe poder convertir implícitamente en el tipo de datos de la otra.</span><span class="sxs-lookup"><span data-stu-id="039d1-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="039d1-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="039d1-108">Result Types</span></span>  
 <span data-ttu-id="039d1-109">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="039d1-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="039d1-110">Para obtener más información acerca de la promoción de tipos implícita, vea [sistema de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="039d1-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="039d1-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="039d1-111">Example</span></span>  
 <span data-ttu-id="039d1-112">La siguiente consulta de Entity SQL usa el operador +  para concatenar dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="039d1-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="039d1-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="039d1-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="039d1-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="039d1-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="039d1-115">Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="039d1-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="039d1-116">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="039d1-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="039d1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="039d1-117">See Also</span></span>  
 [<span data-ttu-id="039d1-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="039d1-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="039d1-119">Tipos de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="039d1-119">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4)
