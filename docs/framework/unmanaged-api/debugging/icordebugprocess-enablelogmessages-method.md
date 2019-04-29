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
ms.openlocfilehash: fe237ca01d409636f184930d26ca970d58e90437
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749525"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="e275b-102">ICorDebugProcess::EnableLogMessages (Método)</span><span class="sxs-lookup"><span data-stu-id="e275b-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="e275b-103">Habilita y deshabilita la transmisión de mensajes de registro en el depurador.</span><span class="sxs-lookup"><span data-stu-id="e275b-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e275b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e275b-104">Syntax</span></span>  
  
```  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e275b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e275b-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="e275b-106">[in] `true` permite la transmisión de mensajes de registro; `false` deshabilita la transmisión.</span><span class="sxs-lookup"><span data-stu-id="e275b-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e275b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e275b-107">Remarks</span></span>  
 <span data-ttu-id="e275b-108">Este método es válido solo después de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) se produce la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e275b-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e275b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e275b-109">Requirements</span></span>  
 <span data-ttu-id="e275b-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e275b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e275b-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e275b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e275b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e275b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e275b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e275b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
