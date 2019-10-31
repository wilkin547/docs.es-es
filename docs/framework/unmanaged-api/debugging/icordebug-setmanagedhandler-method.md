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
ms.openlocfilehash: 88a007654646ba42ebcaf1b42e002282a1040c7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134063"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="5514c-102">ICorDebug::SetManagedHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="5514c-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="5514c-103">Especifica el objeto de controlador de eventos para los eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="5514c-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5514c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5514c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5514c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5514c-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="5514c-106">de Un puntero a un objeto [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) , que es el objeto del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5514c-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5514c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5514c-107">Remarks</span></span>  
 <span data-ttu-id="5514c-108">se debe llamar a `SetManagedHandler` en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="5514c-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="5514c-109">Si la implementación de `ICorDebugManagedCallback` no contiene interfaces suficientes para controlar los eventos de depuración de la aplicación que se está depurando, `SetManagedHandler` devuelve un valor HRESULT de E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="5514c-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5514c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5514c-110">Requirements</span></span>  
 <span data-ttu-id="5514c-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5514c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5514c-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5514c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5514c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5514c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5514c-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5514c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5514c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5514c-115">See also</span></span>

- [<span data-ttu-id="5514c-116">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5514c-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
