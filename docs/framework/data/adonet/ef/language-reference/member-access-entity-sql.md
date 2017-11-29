---
title: . (Acceso a miembros) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c9d5d8f2c90273b316379d3c2803835bab3faef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="3a1d3-103">.</span><span class="sxs-lookup"><span data-stu-id="3a1d3-103">.</span></span> <span data-ttu-id="3a1d3-104">(Acceso a miembros) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3a1d3-104">(Member Access) (Entity SQL)</span></span>
<span data-ttu-id="3a1d3-105">El operador punto (.) es el [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="3a1d3-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="3a1d3-106">El operador de acceso a miembros se usa para obtener el valor de una propiedad o un campo de una instancia de un tipo del modelo conceptual estructural.</span><span class="sxs-lookup"><span data-stu-id="3a1d3-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1d3-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a1d3-107">Syntax</span></span>  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="3a1d3-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3a1d3-108">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3a1d3-109">Instancia de un tipo del modelo conceptual estructural.</span><span class="sxs-lookup"><span data-stu-id="3a1d3-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="3a1d3-110">Propiedad o campo que pertenece a una instancia de objeto.</span><span class="sxs-lookup"><span data-stu-id="3a1d3-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a1d3-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a1d3-111">Remarks</span></span>  
 <span data-ttu-id="3a1d3-112">El operador punto (.) se puede utilizar para extraer campos de un registro, que es similar a extraer propiedades de un tipo complejo o de entidad.</span><span class="sxs-lookup"><span data-stu-id="3a1d3-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="3a1d3-113">Por ejemplo, si n de tipo Name de tipo es miembro de tipo Person, y p es una instancia de tipo Person, p.n es una expresión de acceso a miembros legal que obtiene un valor de tipo Name.</span><span class="sxs-lookup"><span data-stu-id="3a1d3-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="3a1d3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a1d3-114">See Also</span></span>  
 [<span data-ttu-id="3a1d3-115">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3a1d3-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
