---
title: Interfaz ICorDebugThreadEnum
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
ms.openlocfilehash: 6de2cb7c1a1423c5bd38a6f2e5d01c39166ab119
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791317"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="eddcf-102">Interfaz ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="eddcf-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="eddcf-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="eddcf-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eddcf-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="eddcf-104">Methods</span></span>  
  
|<span data-ttu-id="eddcf-105">Método</span><span class="sxs-lookup"><span data-stu-id="eddcf-105">Method</span></span>|<span data-ttu-id="eddcf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="eddcf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eddcf-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="eddcf-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="eddcf-108">Obtiene el número especificado de instancias de `ICorDebugThread` de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="eddcf-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eddcf-109">Notas</span><span class="sxs-lookup"><span data-stu-id="eddcf-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eddcf-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="eddcf-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eddcf-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="eddcf-111">Requirements</span></span>  
 <span data-ttu-id="eddcf-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eddcf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eddcf-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eddcf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eddcf-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eddcf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eddcf-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eddcf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eddcf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="eddcf-116">See also</span></span>

- [<span data-ttu-id="eddcf-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="eddcf-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
