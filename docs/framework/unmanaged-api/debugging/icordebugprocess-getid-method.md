---
title: ICorDebugProcess::GetID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ebdf0dd2457cd10e31ff71c32b1c09d0e014431
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765987"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="68362-102">ICorDebugProcess::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="68362-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="68362-103">Obtiene el identificador de sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="68362-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68362-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68362-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68362-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="68362-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="68362-106">[out] El identificador único del proceso.</span><span class="sxs-lookup"><span data-stu-id="68362-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68362-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68362-107">Requirements</span></span>  
 <span data-ttu-id="68362-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68362-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68362-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68362-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68362-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68362-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68362-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68362-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
