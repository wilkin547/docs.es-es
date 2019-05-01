---
title: Funciones (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: f31f829b53160da5a043617b9aa999b398859f17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034169"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="99ece-102">Funciones (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="99ece-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="99ece-103">Entity SQL admite funciones definidas por el usuario, funciones canónicas y funciones específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="99ece-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="99ece-104">Las funciones definidas por el usuario se especifican en el modelo conceptual o inline en la consulta.</span><span class="sxs-lookup"><span data-stu-id="99ece-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="99ece-105">Para obtener más información, consulte [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="99ece-105">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="99ece-106">Las funciones canónicas se predefinen en el Entity Framework y los proveedores de datos las admiten.</span><span class="sxs-lookup"><span data-stu-id="99ece-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="99ece-107">Se producirá un error en los comandos de Entity SQL si un usuario llama a una función que un proveedor no admita.</span><span class="sxs-lookup"><span data-stu-id="99ece-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="99ece-108">Por consiguiente, las funciones canónicas generalmente se recomiendan sobre las funciones específicas del proveedor, que están en un espacio de nombres concreto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="99ece-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="99ece-109">Para obtener más información, consulte [funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="99ece-109">For more information, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="99ece-110">El proveedor administrado de Microsoft SQL Client proporciona un conjunto de funciones específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="99ece-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="99ece-111">Para obtener más información, consulte [SqlClient para las funciones de Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="99ece-111">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99ece-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="99ece-112">In This Section</span></span>  
 [<span data-ttu-id="99ece-113">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="99ece-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="99ece-114">Resolución de la sobrecarga de funciones</span><span class="sxs-lookup"><span data-stu-id="99ece-114">Function Overload Resolution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="99ece-115">Funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="99ece-115">Aggregate Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="99ece-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="99ece-116">See also</span></span>

- [<span data-ttu-id="99ece-117">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="99ece-117">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
