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
ms.openlocfilehash: d752eb17b956e2367e8b191080a370506a61ff34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416672"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="3c801-102">ICorDebugProcess::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="3c801-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="3c801-103">Obtiene el identificador de sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="3c801-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c801-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c801-104">Syntax</span></span>  
  
```  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c801-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c801-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="3c801-106">[out] El identificador único del proceso.</span><span class="sxs-lookup"><span data-stu-id="3c801-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c801-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c801-107">Requirements</span></span>  
 <span data-ttu-id="3c801-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c801-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c801-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c801-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c801-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c801-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c801-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c801-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
