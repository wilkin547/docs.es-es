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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cb7be64089a55e7b653fcd6272219abba311af8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960809"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="3f04f-102">Interfaz ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="3f04f-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="3f04f-103">Proporciona métodos que amplían las capacidades de "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="3f04f-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f04f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3f04f-104">Methods</span></span>  
  
|<span data-ttu-id="3f04f-105">Método</span><span class="sxs-lookup"><span data-stu-id="3f04f-105">Method</span></span>|<span data-ttu-id="3f04f-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3f04f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f04f-107">GetCodeChunks (método)</span><span class="sxs-lookup"><span data-stu-id="3f04f-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="3f04f-108">Obtiene los fragmentos de código de los que está compuesto este objeto de código.</span><span class="sxs-lookup"><span data-stu-id="3f04f-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="3f04f-109">GetCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="3f04f-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="3f04f-110">Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="3f04f-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f04f-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f04f-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f04f-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3f04f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f04f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f04f-113">Requirements</span></span>  
 <span data-ttu-id="3f04f-114">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f04f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f04f-115">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="3f04f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f04f-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f04f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f04f-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f04f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f04f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f04f-118">See also</span></span>

- [<span data-ttu-id="3f04f-119">ICorDebugCode3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f04f-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="3f04f-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3f04f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
