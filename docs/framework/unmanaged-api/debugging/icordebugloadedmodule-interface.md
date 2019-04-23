---
title: Interfaz de ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e91dda9cbc5957768e98db2b2a9e1026d94c03e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200758"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="89628-102">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="89628-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="89628-103">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="89628-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89628-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="89628-104">Methods</span></span>  
  
|<span data-ttu-id="89628-105">Método</span><span class="sxs-lookup"><span data-stu-id="89628-105">Method</span></span>|<span data-ttu-id="89628-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="89628-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89628-107">GetBaseAddress (método)</span><span class="sxs-lookup"><span data-stu-id="89628-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="89628-108">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="89628-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="89628-109">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="89628-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="89628-110">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="89628-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="89628-111">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="89628-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="89628-112">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="89628-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89628-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89628-113">Remarks</span></span>  
 <span data-ttu-id="89628-114">La interfaz `ICorDebugLoadedModule` es implementada por un depurador y utiliza por interfaces de depuración de CLR para obtener información acerca del módulo cargado desde el depurador.</span><span class="sxs-lookup"><span data-stu-id="89628-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89628-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="89628-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="89628-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="89628-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89628-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89628-117">Requirements</span></span>  
 <span data-ttu-id="89628-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89628-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89628-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89628-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89628-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89628-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89628-121">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89628-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89628-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="89628-122">See also</span></span>

- [<span data-ttu-id="89628-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="89628-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="89628-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="89628-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
