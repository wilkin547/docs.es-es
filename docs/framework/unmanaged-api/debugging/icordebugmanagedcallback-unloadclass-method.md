---
title: ICorDebugManagedCallback::UnloadClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: f2f19987d22502acbe06bd5e5c14b0d6c17cbe24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781580"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="988c6-102">ICorDebugManagedCallback::UnloadClass (Método)</span><span class="sxs-lookup"><span data-stu-id="988c6-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="988c6-103">Notifica al depurador que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="988c6-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="988c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="988c6-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="988c6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="988c6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="988c6-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="988c6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="988c6-107">de Un puntero a un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="988c6-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="988c6-108">Notas</span><span class="sxs-lookup"><span data-stu-id="988c6-108">Remarks</span></span>  
 <span data-ttu-id="988c6-109">No se debe hacer referencia a la clase después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="988c6-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="988c6-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="988c6-110">Requirements</span></span>  
 <span data-ttu-id="988c6-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="988c6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="988c6-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="988c6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="988c6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="988c6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="988c6-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="988c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988c6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="988c6-115">See also</span></span>

- [<span data-ttu-id="988c6-116">LoadClass (método)</span><span class="sxs-lookup"><span data-stu-id="988c6-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="988c6-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="988c6-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
