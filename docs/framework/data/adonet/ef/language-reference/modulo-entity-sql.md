---
title: (Módulo) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: b08689b6f5b17950738c557e02f995fa85aeb35e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160490"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="03a68-102">(Módulo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="03a68-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="03a68-103">Devuelve el resto de una expresión dividida entre otra.</span><span class="sxs-lookup"><span data-stu-id="03a68-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03a68-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="03a68-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="03a68-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="03a68-106">Expresión numérica que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="03a68-106">The numeric expression to divide.</span></span> `dividend` <span data-ttu-id="03a68-107">es cualquier expresión válida de cualquiera de los tipos de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="03a68-107">is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="03a68-108">Expresión numérica entre la que se divide el dividendo.</span><span class="sxs-lookup"><span data-stu-id="03a68-108">The numeric expression to divide the dividend by.</span></span> `divisor` <span data-ttu-id="03a68-109">es cualquier expresión válida de cualquiera de los tipos de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="03a68-109">is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="03a68-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="03a68-110">Result Types</span></span>  
 <span data-ttu-id="03a68-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="03a68-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="03a68-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03a68-112">Example</span></span>  
 <span data-ttu-id="03a68-113">La siguiente consulta de Entity SQL usa el operador aritmético % para devolver el resto de una expresión dividida entre otra.</span><span class="sxs-lookup"><span data-stu-id="03a68-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="03a68-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="03a68-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="03a68-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="03a68-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="03a68-116">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="03a68-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="03a68-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="03a68-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="03a68-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="03a68-118">See also</span></span>

- [<span data-ttu-id="03a68-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="03a68-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
