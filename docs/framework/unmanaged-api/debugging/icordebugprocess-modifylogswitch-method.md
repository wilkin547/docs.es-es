---
title: ICorDebugProcess::ModifyLogSwitch (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b1c85499e5269027da2c2a01ab67aab2c5da626
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775555"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="38314-102">ICorDebugProcess::ModifyLogSwitch (Método)</span><span class="sxs-lookup"><span data-stu-id="38314-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="38314-103">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="38314-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38314-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38314-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38314-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38314-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="38314-106">[in] Un puntero a una cadena que especifica el nombre del modificador de registro.</span><span class="sxs-lookup"><span data-stu-id="38314-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="38314-107">[in] El nivel de gravedad que se establecerá para el modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="38314-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38314-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38314-108">Remarks</span></span>  
 <span data-ttu-id="38314-109">Este método es válido solo después de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) se ha producido la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="38314-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38314-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38314-110">Requirements</span></span>  
 <span data-ttu-id="38314-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38314-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38314-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38314-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38314-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38314-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38314-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38314-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
