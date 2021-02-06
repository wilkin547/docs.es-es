---
description: 'Más información acerca de: ICorDebugManagedCallback:: LoadModule (método)'
title: ICorDebugManagedCallback::LoadModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: 9a547d384b3f450054ebc70072664c6dcfb5992f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660511"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="740e2-103">ICorDebugManagedCallback::LoadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="740e2-103">ICorDebugManagedCallback::LoadModule Method</span></span>

<span data-ttu-id="740e2-104">Notifica al depurador que un módulo de Common Language Runtime (CLR) se ha cargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="740e2-104">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="740e2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="740e2-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="740e2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="740e2-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="740e2-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="740e2-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="740e2-108">de Un puntero a un objeto ICorDebugModule que representa el módulo CLR.</span><span class="sxs-lookup"><span data-stu-id="740e2-108">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="740e2-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="740e2-109">Remarks</span></span>  

 <span data-ttu-id="740e2-110">La `LoadModule` devolución de llamada proporciona un tiempo adecuado para examinar los metadatos del módulo, establecer las marcas de compilador Just-in-Time (JIT) o habilitar o deshabilitar las devoluciones de llamada de carga de clases para el módulo.</span><span class="sxs-lookup"><span data-stu-id="740e2-110">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="740e2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="740e2-111">Requirements</span></span>  

 <span data-ttu-id="740e2-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="740e2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="740e2-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="740e2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="740e2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="740e2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="740e2-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="740e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="740e2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="740e2-116">See also</span></span>

- [<span data-ttu-id="740e2-117">Método UnloadModule</span><span class="sxs-lookup"><span data-stu-id="740e2-117">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="740e2-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="740e2-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
