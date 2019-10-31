---
title: ICorDebugFrame::GetCallee (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: b83dec65e1dd4fc610be3190e8126e6d9d38a6e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121221"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="14db5-102">ICorDebugFrame::GetCallee (Método)</span><span class="sxs-lookup"><span data-stu-id="14db5-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="14db5-103">Obtiene un puntero al objeto ICorDebugFrame en la cadena actual a la que este marco llamó.</span><span class="sxs-lookup"><span data-stu-id="14db5-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14db5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14db5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14db5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14db5-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="14db5-106">enuncia Puntero a la dirección de un objeto `ICorDebugFrame` que representa el marco al que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="14db5-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="14db5-107">Este valor es NULL si el marco de llamada es el marco más interno de la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="14db5-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14db5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14db5-108">Requirements</span></span>  
 <span data-ttu-id="14db5-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14db5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14db5-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14db5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14db5-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14db5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14db5-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14db5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
