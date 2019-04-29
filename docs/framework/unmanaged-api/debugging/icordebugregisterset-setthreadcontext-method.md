---
title: ICorDebugRegisterSet::SetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b1ea34c187de99d23b05b5e1a30c53bc54a6c0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782803"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="e8660-102">ICorDebugRegisterSet::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="e8660-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="e8660-103">`SetThreadContext` no se implementa en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8660-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e8660-104">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="e8660-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8660-105">Utilice la operación de nivel superior [ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) para establecer el contexto de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="e8660-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8660-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8660-106">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e8660-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8660-107">Requirements</span></span>  
 <span data-ttu-id="e8660-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8660-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8660-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8660-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8660-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8660-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8660-111">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="e8660-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8660-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8660-112">See also</span></span>

- [<span data-ttu-id="e8660-113">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8660-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="e8660-114">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8660-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
