---
title: "ICorDebugProcess::GetID (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 74f388c381576ef69352965877df9f07f0e33281
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="5094b-102">ICorDebugProcess::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="5094b-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="5094b-103">Obtiene el identificador de sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="5094b-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5094b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5094b-104">Syntax</span></span>  
  
```  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5094b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5094b-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="5094b-106">[out] El identificador único del proceso.</span><span class="sxs-lookup"><span data-stu-id="5094b-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5094b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5094b-107">Requirements</span></span>  
 <span data-ttu-id="5094b-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5094b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5094b-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5094b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5094b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5094b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5094b-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5094b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
