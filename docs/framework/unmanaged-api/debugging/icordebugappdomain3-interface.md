---
title: ICorDebugAppDomain3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256fd900fa73948b4ca42ac6b6f21f145effc461
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025896"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="3e5f5-102">ICorDebugAppDomain3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e5f5-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="3e5f5-103">Proporciona métodos para recuperar información acerca de las representaciones de tipos en tiempo de ejecución de Windows actualmente cargados en un dominio de aplicación administradas.</span><span class="sxs-lookup"><span data-stu-id="3e5f5-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="3e5f5-104">Esta interfaz es una extensión de las interfaces ICorDebugAppDomain y ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="3e5f5-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e5f5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3e5f5-105">Methods</span></span>  
  
|<span data-ttu-id="3e5f5-106">Método</span><span class="sxs-lookup"><span data-stu-id="3e5f5-106">Method</span></span>|<span data-ttu-id="3e5f5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e5f5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e5f5-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="3e5f5-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="3e5f5-109">Obtiene un enumerador para todos los tipos en tiempo de ejecución de Windows almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="3e5f5-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="3e5f5-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="3e5f5-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="3e5f5-111">Obtiene un enumerador para los tipos en tiempo de ejecución de Windows almacenado en caché en un dominio de aplicación en función de sus identificadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e5f5-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e5f5-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e5f5-112">Remarks</span></span>  
 <span data-ttu-id="3e5f5-113">Esta interfaz está pensada para utilizarse por un depurador junto con una llamada a evaluación de función `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="3e5f5-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="3e5f5-114">Cuando el método recupera los identificadores de interfaz compatibles con un objeto de servidor de Windows en tiempo de ejecución, el depurador puede usar los métodos definidos en esta interfaz para asignarlas a tipos administrados correspondientes a esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="3e5f5-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="3e5f5-115">Para recuperar una instancia de esta interfaz, ejecute `QueryInterface` en una instancia de la interfaz ICorDebugAppDomain o ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="3e5f5-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e5f5-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3e5f5-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e5f5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e5f5-117">Requirements</span></span>  
 <span data-ttu-id="3e5f5-118">**Plataformas:** Windows en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3e5f5-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="3e5f5-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e5f5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e5f5-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e5f5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e5f5-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e5f5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5f5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e5f5-122">See also</span></span>

- [<span data-ttu-id="3e5f5-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3e5f5-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
