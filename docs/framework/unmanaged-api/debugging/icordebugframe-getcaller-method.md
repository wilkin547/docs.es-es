---
title: ICorDebugFrame::GetCaller (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: b52499e509bf172b03b5e4d2b1e4c677dc800281
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690478"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="be894-102">ICorDebugFrame::GetCaller (Método)</span><span class="sxs-lookup"><span data-stu-id="be894-102">ICorDebugFrame::GetCaller Method</span></span>

<span data-ttu-id="be894-103">Obtiene un puntero al objeto ICorDebugFrame en la cadena actual que llamó a este marco.</span><span class="sxs-lookup"><span data-stu-id="be894-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be894-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be894-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be894-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be894-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="be894-106">enuncia Puntero a la dirección de un `ICorDebugFrame` objeto que representa el marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="be894-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="be894-107">Este valor es NULL si el marco llamado es el marco más externo de la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="be894-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be894-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be894-108">Requirements</span></span>  

 <span data-ttu-id="be894-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be894-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be894-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be894-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be894-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be894-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be894-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be894-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
