---
title: ICorDebugBoxValue (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7238574334b599c7922693c7e9a476a51785491
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967335"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="cb4cd-102">ICorDebugBoxValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb4cd-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="cb4cd-103">Una subclase del ICorDebugHeapValue"" que representa un objeto de clase de valor con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="cb4cd-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb4cd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cb4cd-104">Methods</span></span>  
  
|<span data-ttu-id="cb4cd-105">Método</span><span class="sxs-lookup"><span data-stu-id="cb4cd-105">Method</span></span>|<span data-ttu-id="cb4cd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb4cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb4cd-107">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="cb4cd-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="cb4cd-108">Obtiene un puntero de interfaz a la instancia "ICorDebugObjectValue" conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="cb4cd-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb4cd-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb4cd-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb4cd-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="cb4cd-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb4cd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb4cd-111">Requirements</span></span>  
 <span data-ttu-id="cb4cd-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb4cd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb4cd-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb4cd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb4cd-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb4cd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb4cd-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb4cd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4cd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb4cd-116">See also</span></span>
- [<span data-ttu-id="cb4cd-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cb4cd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
