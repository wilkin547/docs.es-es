---
title: "ICorDebugNativeFrame::GetRegisterSet (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28fb7b2fde484e2608a4d84215755df9a77a73b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="56a09-102">ICorDebugNativeFrame::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="56a09-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="56a09-103">Obtiene el conjunto de registros para este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="56a09-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56a09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56a09-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56a09-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56a09-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="56a09-106">[out] Un puntero a la dirección de un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) establece el objeto que representa el registro para este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="56a09-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56a09-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56a09-107">Requirements</span></span>  
 <span data-ttu-id="56a09-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56a09-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56a09-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56a09-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56a09-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56a09-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56a09-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56a09-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56a09-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="56a09-112">See Also</span></span>  
 
