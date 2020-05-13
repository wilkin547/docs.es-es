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
ms.openlocfilehash: b29de0b70daa783197e78fe985d379d4124bc140
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205148"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="7a1b1-102">ICorDebugFrame::GetCaller (Método)</span><span class="sxs-lookup"><span data-stu-id="7a1b1-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="7a1b1-103">Obtiene un puntero al objeto ICorDebugFrame en la cadena actual que llamó a este marco.</span><span class="sxs-lookup"><span data-stu-id="7a1b1-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a1b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a1b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a1b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7a1b1-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="7a1b1-106">enuncia Puntero a la dirección de un `ICorDebugFrame` objeto que representa el marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="7a1b1-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="7a1b1-107">Este valor es NULL si el marco llamado es el marco más externo de la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="7a1b1-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a1b1-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a1b1-108">Requirements</span></span>  
 <span data-ttu-id="7a1b1-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a1b1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a1b1-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a1b1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a1b1-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a1b1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a1b1-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a1b1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
