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
ms.openlocfilehash: 843399b7e3de522e2c4574963897430aa60a5a50
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114792"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="3f659-102">ICorDebugFrame::GetCaller (Método)</span><span class="sxs-lookup"><span data-stu-id="3f659-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="3f659-103">Obtiene un puntero al objeto ICorDebugFrame en la cadena actual que llamó a este marco.</span><span class="sxs-lookup"><span data-stu-id="3f659-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f659-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f659-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f659-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f659-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="3f659-106">enuncia Puntero a la dirección de un objeto `ICorDebugFrame` que representa el marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="3f659-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="3f659-107">Este valor es NULL si el marco llamado es el marco más externo de la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="3f659-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f659-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f659-108">Requirements</span></span>  
 <span data-ttu-id="3f659-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f659-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f659-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f659-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f659-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f659-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f659-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f659-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
