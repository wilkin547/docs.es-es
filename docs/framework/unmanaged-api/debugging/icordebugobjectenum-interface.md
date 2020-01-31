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
ms.openlocfilehash: 0526c050bcf1316eccf2c756a404fbb971e6d7d0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792737"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="1c85a-102">Interfaz ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="1c85a-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="1c85a-103">Implementa los métodos ICorDebugEnum y enumera las matrices de objetos por sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="1c85a-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c85a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1c85a-104">Methods</span></span>  
  
|<span data-ttu-id="1c85a-105">Método</span><span class="sxs-lookup"><span data-stu-id="1c85a-105">Method</span></span>|<span data-ttu-id="1c85a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c85a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c85a-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="1c85a-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="1c85a-108">Obtiene las RVA del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="1c85a-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c85a-109">Notas</span><span class="sxs-lookup"><span data-stu-id="1c85a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c85a-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1c85a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c85a-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1c85a-111">Requirements</span></span>  
 <span data-ttu-id="1c85a-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c85a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c85a-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c85a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c85a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c85a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c85a-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c85a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c85a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c85a-116">See also</span></span>

- [<span data-ttu-id="1c85a-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1c85a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
