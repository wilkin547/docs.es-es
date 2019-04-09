---
title: Interfaz ICorDebugModuleEnum
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26efb3e43642b6d1fd10b084c2b321609c89d89b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146515"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="71a0a-102">Interfaz ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="71a0a-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="71a0a-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="71a0a-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71a0a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="71a0a-104">Methods</span></span>  
  
|<span data-ttu-id="71a0a-105">Método</span><span class="sxs-lookup"><span data-stu-id="71a0a-105">Method</span></span>|<span data-ttu-id="71a0a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a0a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71a0a-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="71a0a-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="71a0a-108">Obtiene el número especificado de `ICorDebugModule` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="71a0a-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71a0a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71a0a-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71a0a-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="71a0a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71a0a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71a0a-111">Requirements</span></span>  
 <span data-ttu-id="71a0a-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71a0a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71a0a-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71a0a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71a0a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71a0a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="71a0a-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="71a0a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="71a0a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="71a0a-116">See also</span></span>

- [<span data-ttu-id="71a0a-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="71a0a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
