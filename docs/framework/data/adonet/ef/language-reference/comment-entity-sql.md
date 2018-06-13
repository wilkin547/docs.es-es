---
title: -- (Comentario) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 4b3c801999d520a775c1a7026c945c027145b59d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764169"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="ad7f6-102">-- (Comentario) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ad7f6-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="ad7f6-103">Las consultas de[!INCLUDE[esql](../../../../../../includes/esql-md.md)] pueden contener comentarios.</span><span class="sxs-lookup"><span data-stu-id="ad7f6-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="ad7f6-104">Dos guiones (`--`) inician una línea de comentario.</span><span class="sxs-lookup"><span data-stu-id="ad7f6-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad7f6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad7f6-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="ad7f6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ad7f6-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="ad7f6-107">Cadena de caracteres que contiene el texto del comentario.</span><span class="sxs-lookup"><span data-stu-id="ad7f6-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad7f6-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad7f6-108">Example</span></span>  
 <span data-ttu-id="ad7f6-109">En la siguiente consulta de Entity SQL se muestra cómo usar los comentarios.</span><span class="sxs-lookup"><span data-stu-id="ad7f6-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="ad7f6-110">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ad7f6-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ad7f6-111">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ad7f6-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ad7f6-112">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ad7f6-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ad7f6-113">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ad7f6-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="ad7f6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad7f6-114">See Also</span></span>  
 [<span data-ttu-id="ad7f6-115">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ad7f6-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="ad7f6-116">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ad7f6-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
