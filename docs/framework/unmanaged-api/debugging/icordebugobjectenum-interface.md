---
title: Interfaz ICorDebugObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: 0594caf53a889d51ea78e2ee9d6fff4d30f7cff2
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205289"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="df872-102">Interfaz ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="df872-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="df872-103">Implementa los métodos ICorDebugEnum y enumera las matrices de objetos por sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="df872-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df872-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="df872-104">Methods</span></span>  
  
|<span data-ttu-id="df872-105">Método</span><span class="sxs-lookup"><span data-stu-id="df872-105">Method</span></span>|<span data-ttu-id="df872-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="df872-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="df872-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="df872-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="df872-108">Obtiene las RVA del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="df872-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df872-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="df872-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df872-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="df872-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df872-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df872-111">Requirements</span></span>  
 <span data-ttu-id="df872-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df872-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df872-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df872-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df872-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df872-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df872-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df872-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df872-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df872-116">See also</span></span>

- [<span data-ttu-id="df872-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="df872-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
