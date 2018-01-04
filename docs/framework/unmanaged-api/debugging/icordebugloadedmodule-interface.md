---
title: Interfaz de ICorDebugLoadedModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4cc7a36deb7c81ccf67427b833dead7127619b39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="e2abd-102">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="e2abd-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="e2abd-103">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="e2abd-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2abd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e2abd-104">Methods</span></span>  
  
|<span data-ttu-id="e2abd-105">Método</span><span class="sxs-lookup"><span data-stu-id="e2abd-105">Method</span></span>|<span data-ttu-id="e2abd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2abd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2abd-107">GetBaseAddress (método)</span><span class="sxs-lookup"><span data-stu-id="e2abd-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="e2abd-108">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="e2abd-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="e2abd-109">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="e2abd-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="e2abd-110">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="e2abd-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="e2abd-111">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="e2abd-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="e2abd-112">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="e2abd-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2abd-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2abd-113">Remarks</span></span>  
 <span data-ttu-id="e2abd-114">La interfaz `ICorDebugLoadedModule` es implementada por un depurador y utiliza por interfaces de depuración de CLR para obtener información acerca del módulo cargado desde el depurador.</span><span class="sxs-lookup"><span data-stu-id="e2abd-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2abd-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e2abd-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e2abd-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="e2abd-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2abd-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2abd-117">Requirements</span></span>  
 <span data-ttu-id="e2abd-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2abd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2abd-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2abd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2abd-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2abd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2abd-121">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2abd-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2abd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2abd-122">See Also</span></span>  
 [<span data-ttu-id="e2abd-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e2abd-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e2abd-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="e2abd-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
