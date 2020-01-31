---
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
ms.openlocfilehash: 161358fab9a4601e7b718321273d493bd84a3228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792012"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="ed107-102">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed107-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="ed107-103">Extiende las capacidades de la interfaz [ICorDebugRegisterSet](icordebugregisterset-interface.md) para plataformas de hardware que tienen más de 64 registros.</span><span class="sxs-lookup"><span data-stu-id="ed107-103">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed107-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ed107-104">Methods</span></span>  
  
|<span data-ttu-id="ed107-105">Método</span><span class="sxs-lookup"><span data-stu-id="ed107-105">Method</span></span>|<span data-ttu-id="ed107-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed107-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed107-107">GetRegisters (método)</span><span class="sxs-lookup"><span data-stu-id="ed107-107">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="ed107-108">Obtiene el valor de cada registro (en el equipo que está ejecutando código actualmente) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="ed107-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="ed107-109">GetRegistersAvailable (método)</span><span class="sxs-lookup"><span data-stu-id="ed107-109">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="ed107-110">Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="ed107-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="ed107-111">SetRegisters (método)</span><span class="sxs-lookup"><span data-stu-id="ed107-111">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="ed107-112">No se implementa en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="ed107-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed107-113">Notas</span><span class="sxs-lookup"><span data-stu-id="ed107-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed107-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ed107-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed107-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ed107-115">Requirements</span></span>  
 <span data-ttu-id="ed107-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed107-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed107-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed107-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed107-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed107-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed107-119">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed107-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed107-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed107-120">See also</span></span>

- [<span data-ttu-id="ed107-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ed107-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ed107-122">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed107-122">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
