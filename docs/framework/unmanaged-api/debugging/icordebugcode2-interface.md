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
ms.openlocfilehash: dce3e3e4baeaa351c5ed1d9e5ca2c03631c3fce4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750116"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="12337-102">Interfaz ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="12337-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="12337-103">Proporciona métodos que amplían las capacidades de "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="12337-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12337-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="12337-104">Methods</span></span>  
  
|<span data-ttu-id="12337-105">Método</span><span class="sxs-lookup"><span data-stu-id="12337-105">Method</span></span>|<span data-ttu-id="12337-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="12337-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12337-107">GetCodeChunks (método)</span><span class="sxs-lookup"><span data-stu-id="12337-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="12337-108">Obtiene los fragmentos de código de los que está compuesto este objeto de código.</span><span class="sxs-lookup"><span data-stu-id="12337-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="12337-109">GetCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="12337-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="12337-110">Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="12337-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12337-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12337-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12337-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="12337-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12337-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12337-113">Requirements</span></span>  
 <span data-ttu-id="12337-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12337-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12337-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12337-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12337-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12337-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12337-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12337-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12337-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="12337-118">See also</span></span>

- [<span data-ttu-id="12337-119">ICorDebugCode3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12337-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="12337-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="12337-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
