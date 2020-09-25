---
title: Funciones (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: bef959ae6a835b5d1d696162528a8f904c59e8e5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201075"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="c59b1-102">Funciones (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c59b1-102">Functions (Entity SQL)</span></span>

<span data-ttu-id="c59b1-103">Entity SQL admite funciones definidas por el usuario, funciones canónicas y funciones específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c59b1-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="c59b1-104">Las funciones definidas por el usuario se especifican en el modelo conceptual o inline en la consulta.</span><span class="sxs-lookup"><span data-stu-id="c59b1-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="c59b1-105">Para obtener más información, vea [funciones definidas por el usuario](user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c59b1-105">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="c59b1-106">Las funciones canónicas se predefinen en el Entity Framework y los proveedores de datos las admiten.</span><span class="sxs-lookup"><span data-stu-id="c59b1-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="c59b1-107">Se producirá un error en los comandos de Entity SQL si un usuario llama a una función que un proveedor no admita.</span><span class="sxs-lookup"><span data-stu-id="c59b1-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="c59b1-108">Por consiguiente, las funciones canónicas generalmente se recomiendan sobre las funciones específicas del proveedor, que están en un espacio de nombres concreto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c59b1-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="c59b1-109">Para obtener más información, vea [funciones canónicas](canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="c59b1-109">For more information, see [Canonical Functions](canonical-functions.md).</span></span>  
  
 <span data-ttu-id="c59b1-110">El proveedor administrado de Microsoft SQL Client proporciona un conjunto de funciones específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c59b1-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="c59b1-111">Para obtener más información, vea [SqlClient para funciones de Entity Framework](../sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="c59b1-111">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c59b1-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c59b1-112">In This Section</span></span>  

 [<span data-ttu-id="c59b1-113">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="c59b1-113">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="c59b1-114">Resolución de la sobrecarga de funciones</span><span class="sxs-lookup"><span data-stu-id="c59b1-114">Function Overload Resolution</span></span>](function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="c59b1-115">Funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="c59b1-115">Aggregate Functions</span></span>](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="c59b1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c59b1-116">See also</span></span>

- [<span data-ttu-id="c59b1-117">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c59b1-117">Entity SQL Overview</span></span>](entity-sql-overview.md)
