---
title: "ICorDebugFrame::GetCaller (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetCaller
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0f426823b0076a8d6bee1b39a7cdcdf618dad90
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="c46f5-102">ICorDebugFrame::GetCaller (Método)</span><span class="sxs-lookup"><span data-stu-id="c46f5-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="c46f5-103">Obtiene un puntero al objeto ICorDebugFrame en la cadena actual que ha llamado este marco.</span><span class="sxs-lookup"><span data-stu-id="c46f5-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c46f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c46f5-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c46f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c46f5-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="c46f5-106">[out] Un puntero a la dirección de un `ICorDebugFrame` objeto que representa el marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="c46f5-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="c46f5-107">Este valor es null si el marco llamado es el más externo en la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="c46f5-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c46f5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c46f5-108">Requirements</span></span>  
 <span data-ttu-id="c46f5-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c46f5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c46f5-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c46f5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c46f5-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c46f5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c46f5-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
