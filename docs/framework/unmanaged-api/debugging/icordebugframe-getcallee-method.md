---
title: "ICorDebugFrame::GetCallee (Método)"
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
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 079d598e54f429fa4dd0b5c0c4cadbe2c66c1d50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="66ece-102">ICorDebugFrame::GetCallee (Método)</span><span class="sxs-lookup"><span data-stu-id="66ece-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="66ece-103">Obtiene un puntero al objeto ICorDebugFrame de la cadena actual que ha llamado este marco.</span><span class="sxs-lookup"><span data-stu-id="66ece-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66ece-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66ece-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66ece-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66ece-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="66ece-106">[out] Un puntero a la dirección de un `ICorDebugFrame` objeto que representa el marco de la llamada.</span><span class="sxs-lookup"><span data-stu-id="66ece-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="66ece-107">Este valor es null si el marco que realiza la llamada es el más interno de la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="66ece-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66ece-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66ece-108">Requirements</span></span>  
 <span data-ttu-id="66ece-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66ece-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66ece-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66ece-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66ece-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66ece-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66ece-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66ece-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
