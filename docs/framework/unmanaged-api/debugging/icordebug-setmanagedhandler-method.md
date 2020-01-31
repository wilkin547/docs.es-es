---
title: ICorDebug::SetManagedHandler (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 54ef1cab27a39de39b39996729be6b8160570745
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788968"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="cf0df-102">ICorDebug::SetManagedHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="cf0df-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="cf0df-103">Especifica el objeto de controlador de eventos para los eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="cf0df-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf0df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf0df-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf0df-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="cf0df-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="cf0df-106">de Un puntero a un objeto [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) , que es el objeto del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cf0df-106">[in] A pointer to an [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf0df-107">Notas</span><span class="sxs-lookup"><span data-stu-id="cf0df-107">Remarks</span></span>  
 <span data-ttu-id="cf0df-108">se debe llamar a `SetManagedHandler` en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="cf0df-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="cf0df-109">Si la implementación de `ICorDebugManagedCallback` no contiene interfaces suficientes para controlar los eventos de depuración de la aplicación que se está depurando, `SetManagedHandler` devuelve un valor HRESULT de E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="cf0df-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf0df-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="cf0df-110">Requirements</span></span>  
 <span data-ttu-id="cf0df-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf0df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf0df-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf0df-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf0df-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf0df-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf0df-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf0df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf0df-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf0df-115">See also</span></span>

- [<span data-ttu-id="cf0df-116">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf0df-116">ICorDebug Interface</span></span>](icordebug-interface.md)
