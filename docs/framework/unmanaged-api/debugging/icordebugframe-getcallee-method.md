---
description: 'Más información sobre: ICorDebugFrame:: Getcallee ((método)'
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
ms.openlocfilehash: 85b64933cb2f180445b88f7b19f8b78f1788252e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693075"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="af7a0-103">ICorDebugFrame::GetCallee (Método)</span><span class="sxs-lookup"><span data-stu-id="af7a0-103">ICorDebugFrame::GetCallee Method</span></span>

<span data-ttu-id="af7a0-104">Obtiene un puntero al objeto ICorDebugFrame en la cadena actual a la que este marco llamó.</span><span class="sxs-lookup"><span data-stu-id="af7a0-104">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af7a0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af7a0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af7a0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af7a0-106">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="af7a0-107">enuncia Puntero a la dirección de un `ICorDebugFrame` objeto que representa el marco al que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="af7a0-107">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="af7a0-108">Este valor es NULL si el marco de llamada es el marco más interno de la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="af7a0-108">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af7a0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af7a0-109">Requirements</span></span>  

 <span data-ttu-id="af7a0-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af7a0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af7a0-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af7a0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af7a0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af7a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af7a0-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af7a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
