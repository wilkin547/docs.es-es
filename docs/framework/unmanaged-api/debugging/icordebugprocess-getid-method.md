---
description: 'Más información acerca de: ICorDebugProcess:: GetID (método)'
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
ms.openlocfilehash: 806e73724a88d08235f4a3e751f771abace1ad56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746989"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="114d8-103">ICorDebugProcess::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="114d8-103">ICorDebugProcess::GetID Method</span></span>

<span data-ttu-id="114d8-104">Obtiene el identificador del sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="114d8-104">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="114d8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="114d8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="114d8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="114d8-106">Parameters</span></span>  

 `pdwProcessId`  
 <span data-ttu-id="114d8-107">enuncia IDENTIFICADOR único del proceso.</span><span class="sxs-lookup"><span data-stu-id="114d8-107">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="114d8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="114d8-108">Requirements</span></span>  

 <span data-ttu-id="114d8-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="114d8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="114d8-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="114d8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="114d8-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="114d8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="114d8-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="114d8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
