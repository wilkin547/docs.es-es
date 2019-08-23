---
title: Interfaz ICorDebugAssembly2
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2
helpviewer_keywords:
- ICorDebugAssembly2 interface [.NET Framework debugging]
ms.assetid: c0766e29-e573-4f9a-a928-167d1de5aa7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b42cb2bff677963c44bfc04f8bdd6c60497e4731
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909894"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="9e704-102">Interfaz ICorDebugAssembly2</span><span class="sxs-lookup"><span data-stu-id="9e704-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="9e704-103">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9e704-103">Represents an assembly.</span></span> <span data-ttu-id="9e704-104">Esta interfaz es una extensión de la interfaz ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="9e704-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e704-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9e704-105">Methods</span></span>  
  
|<span data-ttu-id="9e704-106">Método</span><span class="sxs-lookup"><span data-stu-id="9e704-106">Method</span></span>|<span data-ttu-id="9e704-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9e704-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e704-108">IsFullyTrusted (método)</span><span class="sxs-lookup"><span data-stu-id="9e704-108">IsFullyTrusted Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="9e704-109">Obtiene un valor que indica si el sistema de seguridad en tiempo de ejecución ha concedido plena confianza al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9e704-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e704-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e704-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e704-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9e704-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e704-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e704-112">Requirements</span></span>  
 <span data-ttu-id="9e704-113">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e704-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e704-114">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="9e704-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e704-115">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e704-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e704-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e704-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e704-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e704-117">See also</span></span>

- [<span data-ttu-id="9e704-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9e704-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
