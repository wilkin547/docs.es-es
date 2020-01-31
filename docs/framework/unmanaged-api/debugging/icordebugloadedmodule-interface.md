---
title: ICorDebugLoadedModule (Interfaz)
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 9d3bdcec9e90dab337b595294d114de4bd3d531f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782000"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="05094-102">ICorDebugLoadedModule (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="05094-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="05094-103">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="05094-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05094-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="05094-104">Methods</span></span>  
  
|<span data-ttu-id="05094-105">Método</span><span class="sxs-lookup"><span data-stu-id="05094-105">Method</span></span>|<span data-ttu-id="05094-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="05094-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05094-107">GetBaseAddress (método)</span><span class="sxs-lookup"><span data-stu-id="05094-107">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="05094-108">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="05094-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="05094-109">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="05094-109">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="05094-110">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="05094-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="05094-111">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="05094-111">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="05094-112">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="05094-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05094-113">Notas</span><span class="sxs-lookup"><span data-stu-id="05094-113">Remarks</span></span>  
 <span data-ttu-id="05094-114">La interfaz `ICorDebugLoadedModule` es implementada por un depurador y utiliza por interfaces de depuración de CLR para obtener información acerca del módulo cargado desde el depurador.</span><span class="sxs-lookup"><span data-stu-id="05094-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05094-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05094-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="05094-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="05094-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05094-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="05094-117">Requirements</span></span>  
 <span data-ttu-id="05094-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05094-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05094-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05094-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05094-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05094-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05094-121">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05094-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05094-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="05094-122">See also</span></span>

- [<span data-ttu-id="05094-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="05094-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="05094-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="05094-124">Debugging</span></span>](index.md)
