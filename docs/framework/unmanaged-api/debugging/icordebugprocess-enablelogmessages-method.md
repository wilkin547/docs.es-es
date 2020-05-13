---
title: ICorDebugProcess::EnableLogMessages (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
ms.openlocfilehash: 3b850a462ce354b81f4406fce7fd9d8d9b6013d8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207902"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="03b09-102">ICorDebugProcess::EnableLogMessages (Método)</span><span class="sxs-lookup"><span data-stu-id="03b09-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="03b09-103">Habilita y deshabilita la transmisión de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="03b09-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03b09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03b09-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03b09-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03b09-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="03b09-106">[in] `true` habilita la transmisión de mensajes de registro; `false`deshabilita la transmisión.</span><span class="sxs-lookup"><span data-stu-id="03b09-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03b09-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="03b09-107">Remarks</span></span>  
 <span data-ttu-id="03b09-108">Este método es válido solo después de que se produzca la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="03b09-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03b09-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03b09-109">Requirements</span></span>  
 <span data-ttu-id="03b09-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03b09-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03b09-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03b09-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03b09-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03b09-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03b09-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03b09-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
