---
description: 'Más información acerca de: interfaz ICorDebugRegisterSet2'
title: ICorDebugRegisterSet2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: 3501325df188879f5687347ef329f490b487d9d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803612"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="7b93a-103">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b93a-103">ICorDebugRegisterSet2 Interface</span></span>

<span data-ttu-id="7b93a-104">Extiende las capacidades de la interfaz [ICorDebugRegisterSet](icordebugregisterset-interface.md) para plataformas de hardware que tienen más de 64 registros.</span><span class="sxs-lookup"><span data-stu-id="7b93a-104">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b93a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7b93a-105">Methods</span></span>  
  
|<span data-ttu-id="7b93a-106">Método</span><span class="sxs-lookup"><span data-stu-id="7b93a-106">Method</span></span>|<span data-ttu-id="7b93a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b93a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b93a-108">GetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="7b93a-108">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="7b93a-109">Obtiene el valor de cada registro (en el equipo que está ejecutando código actualmente) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="7b93a-109">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="7b93a-110">GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="7b93a-110">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="7b93a-111">Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="7b93a-111">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="7b93a-112">Método SetRegisters</span><span class="sxs-lookup"><span data-stu-id="7b93a-112">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="7b93a-113">No se implementa en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="7b93a-113">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b93a-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7b93a-114">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b93a-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7b93a-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b93a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b93a-116">Requirements</span></span>  

 <span data-ttu-id="7b93a-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b93a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b93a-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b93a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b93a-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b93a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b93a-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b93a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b93a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b93a-121">See also</span></span>

- [<span data-ttu-id="7b93a-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7b93a-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7b93a-123">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b93a-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
