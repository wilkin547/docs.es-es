---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32f5fc34c4dbde5a5ae04ad95ad5d960e1ceadcd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363671"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="71dd5-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="71dd5-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="71dd5-103">Obtiene la actual [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) objeto en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="71dd5-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="71dd5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71dd5-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="71dd5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71dd5-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="71dd5-106">[out] Un puntero a la actual `ICorDebugManagedCallback3::CustomNotification` objeto en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="71dd5-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="71dd5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71dd5-107">Remarks</span></span>

<span data-ttu-id="71dd5-108">El valor de `ppNotificationObject` es null si no se llama al método desde un `ICorDebugManagedCallback3::CustomNotification` devolución de llamada, o si no existe ningún objeto de notificación actual.</span><span class="sxs-lookup"><span data-stu-id="71dd5-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="71dd5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71dd5-109">Requirements</span></span>

<span data-ttu-id="71dd5-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71dd5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="71dd5-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71dd5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="71dd5-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71dd5-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="71dd5-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71dd5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="71dd5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="71dd5-114">See also</span></span>
- [<span data-ttu-id="71dd5-115">ICorDebugThread4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71dd5-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="71dd5-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="71dd5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="71dd5-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="71dd5-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
