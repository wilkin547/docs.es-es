---
description: 'Más información acerca de: interfaz ICorDebugValue2'
title: ICorDebugValue2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: b408bb5d1732a60fc9aa8ffb93321d3542f2cab7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690267"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="d4c34-103">ICorDebugValue2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4c34-103">ICorDebugValue2 Interface</span></span>

<span data-ttu-id="d4c34-104">Extiende la interfaz "ICorDebugValue" para proporcionar compatibilidad con objetos "ICorDebugType".</span><span class="sxs-lookup"><span data-stu-id="d4c34-104">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4c34-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d4c34-105">Methods</span></span>  
  
|<span data-ttu-id="d4c34-106">Método</span><span class="sxs-lookup"><span data-stu-id="d4c34-106">Method</span></span>|<span data-ttu-id="d4c34-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4c34-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4c34-108">Método GetExactType</span><span class="sxs-lookup"><span data-stu-id="d4c34-108">GetExactType Method</span></span>](icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="d4c34-109">Obtiene un puntero de interfaz a un `ICorDebugType` objeto que representa el <xref:System.Type> de este valor.</span><span class="sxs-lookup"><span data-stu-id="d4c34-109">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4c34-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d4c34-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4c34-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d4c34-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4c34-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4c34-112">Requirements</span></span>  

 <span data-ttu-id="d4c34-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4c34-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4c34-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4c34-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4c34-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4c34-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4c34-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c34-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c34-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4c34-117">See also</span></span>

- [<span data-ttu-id="d4c34-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d4c34-118">Debugging Interfaces</span></span>](debugging-interfaces.md)

- [<span data-ttu-id="d4c34-119">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4c34-119">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
