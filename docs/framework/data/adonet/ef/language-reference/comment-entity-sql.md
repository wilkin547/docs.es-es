---
title: -- (Comentario) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 483e1c69aea94375983acd840f84512de54bc746
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="c35f1-102">-- (Comentario) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c35f1-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="c35f1-103">Las consultas de[!INCLUDE[esql](../../../../../../includes/esql-md.md)] pueden contener comentarios.</span><span class="sxs-lookup"><span data-stu-id="c35f1-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="c35f1-104">Dos guiones (`--`) inician una línea de comentario.</span><span class="sxs-lookup"><span data-stu-id="c35f1-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c35f1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c35f1-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="c35f1-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c35f1-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="c35f1-107">Cadena de caracteres que contiene el texto del comentario.</span><span class="sxs-lookup"><span data-stu-id="c35f1-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c35f1-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c35f1-108">Example</span></span>  
 <span data-ttu-id="c35f1-109">En la siguiente consulta de Entity SQL se muestra cómo usar los comentarios.</span><span class="sxs-lookup"><span data-stu-id="c35f1-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="c35f1-110">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c35f1-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c35f1-111">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c35f1-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c35f1-112">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c35f1-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="c35f1-113">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c35f1-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="c35f1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c35f1-114">See Also</span></span>  
 [<span data-ttu-id="c35f1-115">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c35f1-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="c35f1-116">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c35f1-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
