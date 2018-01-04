---
title: "ICorDebugProcess::ModifyLogSwitch (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.ModifyLogSwitch
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e5fb515229c566ee47bf99fe1a5985389e2a425
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="d1593-102">ICorDebugProcess::ModifyLogSwitch (Método)</span><span class="sxs-lookup"><span data-stu-id="d1593-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="d1593-103">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="d1593-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1593-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1593-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1593-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1593-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="d1593-106">[in] Un puntero a una cadena que especifica el nombre del modificador de registro.</span><span class="sxs-lookup"><span data-stu-id="d1593-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="d1593-107">[in] El nivel de gravedad que se establecerá para el modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="d1593-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1593-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1593-108">Remarks</span></span>  
 <span data-ttu-id="d1593-109">Este método es válido después de la [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) se ha producido la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d1593-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1593-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1593-110">Requirements</span></span>  
 <span data-ttu-id="d1593-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1593-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1593-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1593-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1593-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1593-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1593-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1593-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
