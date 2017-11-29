---
title: "ICorDebugFrame::GetChain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetChain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3fbde18a15b08b8921c6d31f0fb3c19c85c26cfe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="44ce5-102">ICorDebugFrame::GetChain (Método)</span><span class="sxs-lookup"><span data-stu-id="44ce5-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="44ce5-103">Obtiene un puntero a la cadena de de que este marco es una parte.</span><span class="sxs-lookup"><span data-stu-id="44ce5-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44ce5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44ce5-104">Syntax</span></span>  
  
```  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44ce5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44ce5-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="44ce5-106">[out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena que contiene este marco.</span><span class="sxs-lookup"><span data-stu-id="44ce5-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44ce5-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44ce5-107">Requirements</span></span>  
 <span data-ttu-id="44ce5-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44ce5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44ce5-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44ce5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44ce5-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44ce5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44ce5-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44ce5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
