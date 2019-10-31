---
title: ICorDebugManagedCallback::UnloadAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: 4ae4856eca2c1441ea53df0d9ed3648700b39b24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130650"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="ac263-102">ICorDebugManagedCallback::UnloadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="ac263-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="ac263-103">Notifica al depurador que se ha descargado un ensamblado de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ac263-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac263-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac263-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac263-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac263-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ac263-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac263-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="ac263-107">de Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac263-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac263-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac263-108">Remarks</span></span>  
 <span data-ttu-id="ac263-109">El ensamblado no se debe utilizar después de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="ac263-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac263-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac263-110">Requirements</span></span>  
 <span data-ttu-id="ac263-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac263-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac263-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac263-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac263-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac263-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac263-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac263-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac263-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac263-115">See also</span></span>

- [<span data-ttu-id="ac263-116">LoadAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="ac263-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="ac263-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac263-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
