---
title: "ICorDebugThread::GetActiveFrame (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetActiveFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8b5d9d42b7c3f7827ce938fdd3dffe57b00142c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="24315-102">ICorDebugThread::GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="24315-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="24315-103">Obtiene un puntero de interfaz al marco activo (más reciente) en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="24315-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24315-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24315-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24315-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24315-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="24315-106">[out] Un puntero a la dirección de un objeto de interfaz de ICorDebugFrame que representa un marco.</span><span class="sxs-lookup"><span data-stu-id="24315-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24315-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24315-107">Remarks</span></span>  
 <span data-ttu-id="24315-108">El `ppFrame` del parámetro es null si ningún marco está activo actualmente.</span><span class="sxs-lookup"><span data-stu-id="24315-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24315-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24315-109">Requirements</span></span>  
 <span data-ttu-id="24315-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24315-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24315-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24315-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24315-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24315-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24315-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24315-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
