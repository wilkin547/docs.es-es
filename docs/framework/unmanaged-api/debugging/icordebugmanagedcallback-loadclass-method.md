---
title: ICorDebugManagedCallback::LoadClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3c430e18864c0352b43641bce9a7d52af69cc80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718226"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="45f91-102">ICorDebugManagedCallback::LoadClass (Método)</span><span class="sxs-lookup"><span data-stu-id="45f91-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="45f91-103">Notifica al depurador que se ha cargado una clase.</span><span class="sxs-lookup"><span data-stu-id="45f91-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45f91-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45f91-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45f91-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45f91-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="45f91-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en la que se ha cargado la clase.</span><span class="sxs-lookup"><span data-stu-id="45f91-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="45f91-107">[in] Un puntero a un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="45f91-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45f91-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45f91-108">Remarks</span></span>  
 <span data-ttu-id="45f91-109">Esta devolución de llamada solo se produce si se ha habilitado la carga de clases para el módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="45f91-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="45f91-110">Carga de las clases siempre está habilitada para los módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="45f91-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="45f91-111">El `LoadClass` devolución de llamada proporciona un tiempo adecuado para enlazar los puntos de interrupción a las clases recién generadas en módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="45f91-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45f91-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45f91-112">Requirements</span></span>  
 <span data-ttu-id="45f91-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45f91-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45f91-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45f91-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45f91-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45f91-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45f91-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45f91-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f91-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="45f91-117">See also</span></span>
- [<span data-ttu-id="45f91-118">UnloadClass (método)</span><span class="sxs-lookup"><span data-stu-id="45f91-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="45f91-119">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45f91-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
