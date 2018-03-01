---
title: "ICorDebugModule::GetProcess (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bdb1337b6aebdb34b76adbbd2fd54d019b5b2abf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="4f499-102">ICorDebugModule::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="4f499-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="4f499-103">Obtiene el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="4f499-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f499-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f499-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f499-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f499-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="4f499-106">[out] Un puntero a la dirección de un objeto ICorDebugProcess que representa el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="4f499-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f499-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f499-107">Requirements</span></span>  
 <span data-ttu-id="4f499-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f499-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f499-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f499-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f499-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f499-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f499-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f499-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
