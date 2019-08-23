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
ms.openlocfilehash: c48c222a34e2e78f29c33e49da331d97d409bae1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949758"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="6673a-102">Interfaz ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="6673a-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="6673a-103">Proporciona el `Next` método, que devuelve un número especificado de `ICorDebugAppDomainEnum` valores a partir de la siguiente ubicación de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="6673a-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="6673a-104">Esta interfaz es una subclase de "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="6673a-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6673a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6673a-105">Methods</span></span>  
  
|<span data-ttu-id="6673a-106">Método</span><span class="sxs-lookup"><span data-stu-id="6673a-106">Method</span></span>|<span data-ttu-id="6673a-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6673a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6673a-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="6673a-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="6673a-109">Obtiene el número especificado de dominios de aplicación de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="6673a-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6673a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6673a-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6673a-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6673a-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6673a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6673a-112">Requirements</span></span>  
 <span data-ttu-id="6673a-113">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6673a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6673a-114">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="6673a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6673a-115">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6673a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6673a-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6673a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6673a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6673a-117">See also</span></span>

- [<span data-ttu-id="6673a-118">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6673a-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="6673a-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6673a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
