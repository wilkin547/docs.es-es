---
description: 'Más información acerca de: ICorDebugThread:: GetActiveFrame ((método)'
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
ms.openlocfilehash: 3b15aad39503dfec9ac8f98f839ee1a6b16b3f90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659267"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="fe0d1-103">ICorDebugThread::GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="fe0d1-103">ICorDebugThread::GetActiveFrame Method</span></span>

<span data-ttu-id="fe0d1-104">Obtiene un puntero de interfaz al marco activo (más reciente) en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="fe0d1-104">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe0d1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe0d1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe0d1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe0d1-106">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="fe0d1-107">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugFrame que representa un marco.</span><span class="sxs-lookup"><span data-stu-id="fe0d1-107">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe0d1-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fe0d1-108">Remarks</span></span>  

 <span data-ttu-id="fe0d1-109">El `ppFrame` parámetro es NULL si no hay ningún marco activo actualmente.</span><span class="sxs-lookup"><span data-stu-id="fe0d1-109">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe0d1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe0d1-110">Requirements</span></span>  

 <span data-ttu-id="fe0d1-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe0d1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe0d1-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe0d1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe0d1-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe0d1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe0d1-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe0d1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
