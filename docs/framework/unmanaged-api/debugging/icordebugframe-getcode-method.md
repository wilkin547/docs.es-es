---
title: "ICorDebugFrame::GetCode (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a99b652a439a284033f3e7a9ecc46b3599fae00b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="9d6f6-102">ICorDebugFrame::GetCode (Método)</span><span class="sxs-lookup"><span data-stu-id="9d6f6-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="9d6f6-103">Obtiene un puntero al código asociado con este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="9d6f6-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d6f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d6f6-104">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d6f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d6f6-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="9d6f6-106">[out] Un puntero a la dirección de un objeto ICorDebugCode que representa el código asociado a este marco.</span><span class="sxs-lookup"><span data-stu-id="9d6f6-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d6f6-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d6f6-107">Requirements</span></span>  
 <span data-ttu-id="9d6f6-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d6f6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d6f6-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d6f6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d6f6-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d6f6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d6f6-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d6f6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
