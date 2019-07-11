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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b199d3226ec391fadc356b5efacdbf10a3e25adf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766160"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="cd033-102">ICorDebugProcess::EnableLogMessages (Método)</span><span class="sxs-lookup"><span data-stu-id="cd033-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="cd033-103">Habilita y deshabilita la transmisión de mensajes de registro en el depurador.</span><span class="sxs-lookup"><span data-stu-id="cd033-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd033-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd033-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd033-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd033-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="cd033-106">[in] `true` permite la transmisión de mensajes de registro; `false` deshabilita la transmisión.</span><span class="sxs-lookup"><span data-stu-id="cd033-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd033-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd033-107">Remarks</span></span>  
 <span data-ttu-id="cd033-108">Este método es válido solo después de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) se produce la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="cd033-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd033-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd033-109">Requirements</span></span>  
 <span data-ttu-id="cd033-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd033-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd033-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd033-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd033-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd033-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd033-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd033-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
