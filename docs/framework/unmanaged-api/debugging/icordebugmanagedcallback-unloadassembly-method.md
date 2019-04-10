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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e770602858761dbcf15c233dceebfd35be106aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214136"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="c3b57-102">ICorDebugManagedCallback::UnloadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="c3b57-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="c3b57-103">Notifica al depurador que se ha descargado un ensamblado de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="c3b57-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3b57-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b57-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3b57-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c3b57-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c3b57-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="c3b57-107">[in] Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c3b57-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3b57-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3b57-108">Remarks</span></span>  
 <span data-ttu-id="c3b57-109">El ensamblado no debe utilizarse después de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="c3b57-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b57-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3b57-110">Requirements</span></span>  
 <span data-ttu-id="c3b57-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3b57-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3b57-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3b57-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3b57-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3b57-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c3b57-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c3b57-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c3b57-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3b57-115">See also</span></span>

- [<span data-ttu-id="c3b57-116">Método LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="c3b57-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="c3b57-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3b57-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
