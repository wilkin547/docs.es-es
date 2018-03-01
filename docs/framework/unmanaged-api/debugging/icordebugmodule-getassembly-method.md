---
title: "ICorDebugModule::GetAssembly (Método)"
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
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b359b68c1bff91e1077afe8ccf52befe22c246b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="489f1-102">ICorDebugModule::GetAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="489f1-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="489f1-103">Obtiene el ensamblado que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="489f1-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="489f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="489f1-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="489f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="489f1-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="489f1-106">[out] Un puntero a un objeto ICorDebugAssembly que representa el ensamblado que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="489f1-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="489f1-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="489f1-107">Requirements</span></span>  
 <span data-ttu-id="489f1-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="489f1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="489f1-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="489f1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="489f1-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="489f1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="489f1-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="489f1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
