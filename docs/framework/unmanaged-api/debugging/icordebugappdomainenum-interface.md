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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155199"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="cd88f-102">Interfaz ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="cd88f-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="cd88f-103">Proporciona el `Next` método, que devuelve un número especificado de `ICorDebugAppDomainEnum` valores a partir de la ubicación siguiente en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="cd88f-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="cd88f-104">Esta interfaz es una subclase de "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="cd88f-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd88f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cd88f-105">Methods</span></span>  
  
|<span data-ttu-id="cd88f-106">Método</span><span class="sxs-lookup"><span data-stu-id="cd88f-106">Method</span></span>|<span data-ttu-id="cd88f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd88f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd88f-108">Método Next</span><span class="sxs-lookup"><span data-stu-id="cd88f-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="cd88f-109">Obtiene el número especificado de dominios de aplicación de la colección, empezando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="cd88f-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd88f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd88f-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd88f-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="cd88f-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd88f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd88f-112">Requirements</span></span>  
 <span data-ttu-id="cd88f-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd88f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd88f-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd88f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd88f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd88f-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cd88f-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cd88f-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cd88f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd88f-117">See also</span></span>

- [<span data-ttu-id="cd88f-118">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd88f-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="cd88f-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cd88f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
