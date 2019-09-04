---
title: Funciones (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: ec94a0f16fb3b836297f6675cc938a711816555b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250914"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="7e812-102">Funciones (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7e812-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="7e812-103">Entity SQL admite funciones definidas por el usuario, funciones canónicas y funciones específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="7e812-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="7e812-104">Las funciones definidas por el usuario se especifican en el modelo conceptual o inline en la consulta.</span><span class="sxs-lookup"><span data-stu-id="7e812-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="7e812-105">Para obtener más información, vea [funciones definidas por el usuario](user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7e812-105">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="7e812-106">Las funciones canónicas se predefinen en el Entity Framework y los proveedores de datos las admiten.</span><span class="sxs-lookup"><span data-stu-id="7e812-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="7e812-107">Se producirá un error en los comandos de Entity SQL si un usuario llama a una función que un proveedor no admita.</span><span class="sxs-lookup"><span data-stu-id="7e812-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="7e812-108">Por consiguiente, las funciones canónicas generalmente se recomiendan sobre las funciones específicas del proveedor, que están en un espacio de nombres concreto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="7e812-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="7e812-109">Para obtener más información, vea [funciones canónicas](canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="7e812-109">For more information, see [Canonical Functions](canonical-functions.md).</span></span>  
  
 <span data-ttu-id="7e812-110">El proveedor administrado de Microsoft SQL Client proporciona un conjunto de funciones específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="7e812-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="7e812-111">Para obtener más información, vea [SqlClient para funciones de Entity Framework](../sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="7e812-111">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7e812-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7e812-112">In This Section</span></span>  
 [<span data-ttu-id="7e812-113">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="7e812-113">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="7e812-114">Resolución de la sobrecarga de funciones</span><span class="sxs-lookup"><span data-stu-id="7e812-114">Function Overload Resolution</span></span>](function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="7e812-115">Funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="7e812-115">Aggregate Functions</span></span>](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="7e812-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e812-116">See also</span></span>

- [<span data-ttu-id="7e812-117">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7e812-117">Entity SQL Overview</span></span>](entity-sql-overview.md)
