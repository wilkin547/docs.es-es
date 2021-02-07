---
description: Más información acerca de:. (Acceso a miembros) (Entity SQL)
title: . (Acceso a miembros) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 94833d3525c7d17cadaef15065b3dcbdb43a6ded
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739383"
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="30e34-105">.</span><span class="sxs-lookup"><span data-stu-id="30e34-105">.</span></span> <span data-ttu-id="30e34-106">(Acceso a miembros) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="30e34-106">(Member Access) (Entity SQL)</span></span>

<span data-ttu-id="30e34-107">El operador punto (.) es el [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operador de acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="30e34-107">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="30e34-108">El operador de acceso a miembros se usa para obtener el valor de una propiedad o un campo de una instancia de un tipo del modelo conceptual estructural.</span><span class="sxs-lookup"><span data-stu-id="30e34-108">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e34-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30e34-109">Syntax</span></span>  
  
```sql  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="30e34-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="30e34-110">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="30e34-111">Instancia de un tipo del modelo conceptual estructural.</span><span class="sxs-lookup"><span data-stu-id="30e34-111">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="30e34-112">Propiedad o campo que pertenece a una instancia de objeto.</span><span class="sxs-lookup"><span data-stu-id="30e34-112">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30e34-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="30e34-113">Remarks</span></span>  

 <span data-ttu-id="30e34-114">El operador punto (.) se puede utilizar para extraer campos de un registro, que es similar a extraer propiedades de un tipo complejo o de entidad.</span><span class="sxs-lookup"><span data-stu-id="30e34-114">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="30e34-115">Por ejemplo, si n de tipo Name de tipo es miembro de tipo Person, y p es una instancia de tipo Person, p.n es una expresión de acceso a miembros legal que obtiene un valor de tipo Name.</span><span class="sxs-lookup"><span data-stu-id="30e34-115">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="30e34-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="30e34-116">See also</span></span>

- [<span data-ttu-id="30e34-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="30e34-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
