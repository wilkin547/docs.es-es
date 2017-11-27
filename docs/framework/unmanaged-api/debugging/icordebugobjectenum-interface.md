---
title: ICorDebugObjectEnum Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectEnum
helpviewer_keywords: ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: baa8ea056c457455482a5f7631956f7edce0ac91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectenum-interface1"></a><span data-ttu-id="f59a4-102">ICorDebugObjectEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="f59a4-102">ICorDebugObjectEnum Interface1</span></span>
<span data-ttu-id="f59a4-103">Implementa los métodos ICorDebugEnum y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="f59a4-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f59a4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f59a4-104">Methods</span></span>  
  
|<span data-ttu-id="f59a4-105">Método</span><span class="sxs-lookup"><span data-stu-id="f59a4-105">Method</span></span>|<span data-ttu-id="f59a4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f59a4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f59a4-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="f59a4-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="f59a4-108">Obtiene las RVA del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f59a4-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f59a4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f59a4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f59a4-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f59a4-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f59a4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f59a4-111">Requirements</span></span>  
 <span data-ttu-id="f59a4-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f59a4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f59a4-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f59a4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f59a4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f59a4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f59a4-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f59a4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f59a4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f59a4-116">See Also</span></span>  
 [<span data-ttu-id="f59a4-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f59a4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
