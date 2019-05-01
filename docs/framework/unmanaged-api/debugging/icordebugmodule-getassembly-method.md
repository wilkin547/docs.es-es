---
title: ICorDebugModule::GetAssembly (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce1e42d74dc611032d941e833bb8f248a56488b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988070"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="2f7c4-102">ICorDebugModule::GetAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="2f7c4-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="2f7c4-103">Obtiene el ensamblado que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="2f7c4-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f7c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f7c4-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f7c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2f7c4-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="2f7c4-106">[out] Un puntero a un objeto ICorDebugAssembly que representa el ensamblado que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="2f7c4-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f7c4-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f7c4-107">Requirements</span></span>  
 <span data-ttu-id="2f7c4-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f7c4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f7c4-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f7c4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f7c4-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f7c4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f7c4-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f7c4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
