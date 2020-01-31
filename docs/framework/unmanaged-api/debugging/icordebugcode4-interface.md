---
title: Interfaz ICorDebugCode4
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
ms.openlocfilehash: 373df8a47bdcbc833ffaea05bb205a63b5f583ec
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777768"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="3dcdf-102">Interfaz ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="3dcdf-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="3dcdf-103">Proporciona un método que permite a un depurador enumerar las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="3dcdf-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3dcdf-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3dcdf-104">Methods</span></span>  
  
|<span data-ttu-id="3dcdf-105">Método</span><span class="sxs-lookup"><span data-stu-id="3dcdf-105">Method</span></span>|<span data-ttu-id="3dcdf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3dcdf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3dcdf-107">EnumerateVariableHomes (método)</span><span class="sxs-lookup"><span data-stu-id="3dcdf-107">EnumerateVariableHomes Method</span></span>](icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="3dcdf-108">Obtiene un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="3dcdf-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dcdf-109">Notas</span><span class="sxs-lookup"><span data-stu-id="3dcdf-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3dcdf-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3dcdf-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dcdf-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3dcdf-111">Requirements</span></span>  
 <span data-ttu-id="3dcdf-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dcdf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dcdf-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dcdf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dcdf-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dcdf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dcdf-115">**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dcdf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dcdf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dcdf-116">See also</span></span>

- [<span data-ttu-id="3dcdf-117">ICorDebugCode3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3dcdf-117">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="3dcdf-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3dcdf-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
