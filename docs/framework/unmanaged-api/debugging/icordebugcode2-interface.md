---
title: Interfaz ICorDebugCode2
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: a9ce778cfa1aed4dcf6117c4fe2eca23ccda37a3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777947"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="6d225-102">Interfaz ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="6d225-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="6d225-103">Proporciona métodos que amplían las capacidades de "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="6d225-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d225-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6d225-104">Methods</span></span>  
  
|<span data-ttu-id="6d225-105">Método</span><span class="sxs-lookup"><span data-stu-id="6d225-105">Method</span></span>|<span data-ttu-id="6d225-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d225-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d225-107">GetCodeChunks (método)</span><span class="sxs-lookup"><span data-stu-id="6d225-107">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="6d225-108">Obtiene los fragmentos de código de los que está compuesto este objeto de código.</span><span class="sxs-lookup"><span data-stu-id="6d225-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="6d225-109">GetCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="6d225-109">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="6d225-110">Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="6d225-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d225-111">Notas</span><span class="sxs-lookup"><span data-stu-id="6d225-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d225-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6d225-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d225-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6d225-113">Requirements</span></span>  
 <span data-ttu-id="6d225-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d225-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d225-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d225-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d225-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d225-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d225-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d225-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d225-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d225-118">See also</span></span>

- [<span data-ttu-id="6d225-119">ICorDebugCode3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d225-119">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="6d225-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6d225-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
