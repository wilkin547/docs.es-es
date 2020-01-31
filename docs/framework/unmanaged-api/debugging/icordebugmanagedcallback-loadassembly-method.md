---
title: ICorDebugManagedCallback::LoadAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
ms.openlocfilehash: 80836cbbf82a97ccd6dc7251e5cbe934e0cbe66f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777278"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="2fd6e-102">ICorDebugManagedCallback::LoadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="2fd6e-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="2fd6e-103">Notifica al depurador que se ha cargado correctamente un ensamblado Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2fd6e-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd6e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fd6e-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fd6e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2fd6e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2fd6e-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2fd6e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="2fd6e-107">de Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2fd6e-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fd6e-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2fd6e-108">Requirements</span></span>  
 <span data-ttu-id="2fd6e-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fd6e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fd6e-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fd6e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fd6e-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fd6e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fd6e-112">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fd6e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd6e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fd6e-113">See also</span></span>

- [<span data-ttu-id="2fd6e-114">UnloadAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="2fd6e-114">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="2fd6e-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fd6e-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
