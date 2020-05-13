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
ms.openlocfilehash: 76ad1c0ac421f05cf30f6d3d1f3e65848796a0c7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378695"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="c3a36-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="c3a36-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="c3a36-103">Obtiene el objeto [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) actual en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c3a36-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3a36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3a36-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="c3a36-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3a36-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="c3a36-106">enuncia Puntero al `ICorDebugManagedCallback3::CustomNotification` objeto actual en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c3a36-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3a36-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c3a36-107">Remarks</span></span>

<span data-ttu-id="c3a36-108">El valor de `ppNotificationObject` es NULL si no se llama al método desde una `ICorDebugManagedCallback3::CustomNotification` devolución de llamada o si no existe ningún objeto de notificación actual.</span><span class="sxs-lookup"><span data-stu-id="c3a36-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="c3a36-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3a36-109">Requirements</span></span>

<span data-ttu-id="c3a36-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3a36-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c3a36-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3a36-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="c3a36-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3a36-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c3a36-113">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3a36-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c3a36-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3a36-114">See also</span></span>

- [<span data-ttu-id="c3a36-115">ICorDebugThread4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3a36-115">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="c3a36-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c3a36-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c3a36-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="c3a36-117">Debugging</span></span>](index.md)
