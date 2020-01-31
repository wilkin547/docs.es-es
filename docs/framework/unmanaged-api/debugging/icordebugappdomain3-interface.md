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
ms.openlocfilehash: 1aaccb37ec61ed1ba6a7e6e1f508704973117cca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784884"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="8983c-102">ICorDebugAppDomain3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8983c-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="8983c-103">Proporciona métodos para recuperar información sobre las representaciones administradas de Windows Runtime tipos cargados actualmente en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8983c-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="8983c-104">Esta interfaz es una extensión de las interfaces ICorDebugAppDomain e ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="8983c-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8983c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8983c-105">Methods</span></span>  
  
|<span data-ttu-id="8983c-106">Método</span><span class="sxs-lookup"><span data-stu-id="8983c-106">Method</span></span>|<span data-ttu-id="8983c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8983c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8983c-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="8983c-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="8983c-109">Obtiene un enumerador para todos los tipos de Windows Runtime almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="8983c-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="8983c-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="8983c-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="8983c-111">Obtiene un enumerador para los tipos de Windows Runtime almacenados en memoria caché en un dominio de aplicación en función de sus identificadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="8983c-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8983c-112">Notas</span><span class="sxs-lookup"><span data-stu-id="8983c-112">Remarks</span></span>  
 <span data-ttu-id="8983c-113">Esta interfaz está pensada para que la use un depurador junto con una llamada de evaluación de función para `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="8983c-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="8983c-114">Cuando el método recupera los identificadores de interfaz admitidos por un objeto de servidor Windows Runtime, el depurador puede usar los métodos definidos en esta interfaz para asignarlos a tipos administrados que corresponden a esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="8983c-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="8983c-115">Para recuperar una instancia de esta interfaz, ejecute `QueryInterface` en una instancia de la interfaz ICorDebugAppDomain o ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="8983c-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8983c-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8983c-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8983c-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="8983c-117">Requirements</span></span>  
 <span data-ttu-id="8983c-118">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="8983c-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="8983c-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8983c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8983c-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8983c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8983c-121">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8983c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8983c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8983c-122">See also</span></span>

- [<span data-ttu-id="8983c-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8983c-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
