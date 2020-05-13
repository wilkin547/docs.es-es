---
title: Interfaz ICorDebugFrameEnum
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
ms.openlocfilehash: 4bc8d56bf116cd64e3e1c5d2238e557784c56711
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209609"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="c2d16-102">Interfaz ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="c2d16-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="c2d16-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="c2d16-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2d16-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c2d16-104">Methods</span></span>  
  
|<span data-ttu-id="c2d16-105">Método</span><span class="sxs-lookup"><span data-stu-id="c2d16-105">Method</span></span>|<span data-ttu-id="c2d16-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2d16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2d16-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="c2d16-107">Next Method</span></span>](icordebugframeenum-next-method.md)|<span data-ttu-id="c2d16-108">Obtiene el número especificado de `ICorDebugFrame` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="c2d16-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2d16-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c2d16-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2d16-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c2d16-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2d16-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2d16-111">Requirements</span></span>  
 <span data-ttu-id="c2d16-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2d16-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2d16-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2d16-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2d16-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2d16-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2d16-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d16-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d16-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2d16-116">See also</span></span>

- [<span data-ttu-id="c2d16-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c2d16-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
