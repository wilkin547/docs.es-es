---
title: "ICorDebugProcess::EnableLogMessages (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.EnableLogMessages
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c67d211e9408cec54d069c4d9bad963aeabb09d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="f6951-102">ICorDebugProcess::EnableLogMessages (Método)</span><span class="sxs-lookup"><span data-stu-id="f6951-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="f6951-103">Habilita y deshabilita la transmisión de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="f6951-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6951-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6951-104">Syntax</span></span>  
  
```  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6951-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6951-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="f6951-106">[in] `true` permite la transmisión de mensajes de registro; `false` deshabilita la transmisión.</span><span class="sxs-lookup"><span data-stu-id="f6951-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6951-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6951-107">Remarks</span></span>  
 <span data-ttu-id="f6951-108">Este método es válido después de la [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) se produce la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f6951-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6951-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6951-109">Requirements</span></span>  
 <span data-ttu-id="f6951-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6951-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6951-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6951-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6951-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6951-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6951-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6951-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
