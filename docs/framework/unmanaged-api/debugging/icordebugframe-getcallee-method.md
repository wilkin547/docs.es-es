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
ms.openlocfilehash: 51ac10f936db129282720f2bcae8729f56735b59
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205379"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="b0a9c-102">ICorDebugFrame::GetCallee (Método)</span><span class="sxs-lookup"><span data-stu-id="b0a9c-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="b0a9c-103">Obtiene un puntero al objeto ICorDebugFrame en la cadena actual a la que este marco llamó.</span><span class="sxs-lookup"><span data-stu-id="b0a9c-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a9c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0a9c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0a9c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0a9c-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="b0a9c-106">enuncia Puntero a la dirección de un `ICorDebugFrame` objeto que representa el marco al que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="b0a9c-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="b0a9c-107">Este valor es NULL si el marco de llamada es el marco más interno de la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="b0a9c-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0a9c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0a9c-108">Requirements</span></span>  
 <span data-ttu-id="b0a9c-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0a9c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0a9c-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0a9c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0a9c-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0a9c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0a9c-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0a9c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
