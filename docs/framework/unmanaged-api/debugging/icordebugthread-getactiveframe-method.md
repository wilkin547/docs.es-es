---
title: ICorDebugThread::GetActiveFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 051491173bbcef3d87d9a3dbe854eece46c49e0d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468785"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="f5817-102">ICorDebugThread::GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="f5817-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="f5817-103">Obtiene un puntero de interfaz al marco activo (más reciente) en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f5817-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5817-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5817-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5817-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5817-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="f5817-106">[out] Un puntero a la dirección de un objeto de interfaz ICorDebugFrame que representa un marco.</span><span class="sxs-lookup"><span data-stu-id="f5817-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5817-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5817-107">Remarks</span></span>  
 <span data-ttu-id="f5817-108">El `ppFrame` parámetro es nulo si ningún marco está activo actualmente.</span><span class="sxs-lookup"><span data-stu-id="f5817-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5817-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5817-109">Requirements</span></span>  
 <span data-ttu-id="f5817-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5817-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5817-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5817-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5817-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5817-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5817-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5817-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
