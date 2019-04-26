---
title: Interfaz ICorDebugAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da1fc949109455cf50767191a99a8a727116f77c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989513"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="dc5d0-102">Interfaz ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="dc5d0-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="dc5d0-103">Proporciona el `Next` método, que devuelve un número especificado de `ICorDebugAppDomainEnum` valores a partir de la ubicación siguiente en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="dc5d0-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="dc5d0-104">Esta interfaz es una subclase de "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="dc5d0-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc5d0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dc5d0-105">Methods</span></span>  
  
|<span data-ttu-id="dc5d0-106">Método</span><span class="sxs-lookup"><span data-stu-id="dc5d0-106">Method</span></span>|<span data-ttu-id="dc5d0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc5d0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc5d0-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="dc5d0-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="dc5d0-109">Obtiene el número especificado de dominios de aplicación de la colección, empezando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="dc5d0-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc5d0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc5d0-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc5d0-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="dc5d0-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc5d0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc5d0-112">Requirements</span></span>  
 <span data-ttu-id="dc5d0-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc5d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc5d0-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc5d0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc5d0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc5d0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc5d0-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc5d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc5d0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc5d0-117">See also</span></span>

- [<span data-ttu-id="dc5d0-118">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc5d0-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="dc5d0-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="dc5d0-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
