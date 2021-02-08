---
description: 'Más información sobre: ICorDebugInternalFrame (:: GetFrameType ((método)'
title: ICorDebugInternalFrame::GetFrameType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
ms.openlocfilehash: ea96f032ebfa5914503287d124242b74a84ea11f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791184"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="63093-103">ICorDebugInternalFrame::GetFrameType (Método)</span><span class="sxs-lookup"><span data-stu-id="63093-103">ICorDebugInternalFrame::GetFrameType Method</span></span>

<span data-ttu-id="63093-104">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="63093-104">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63093-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63093-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63093-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63093-106">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="63093-107">enuncia Un puntero a un valor de la enumeración CorDebugInternalFrameType (que indica el tipo de marco interno representado por este `ICorDebugInternalFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="63093-107">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63093-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="63093-108">Remarks</span></span>  

 <span data-ttu-id="63093-109">El tipo de marco interno nunca se STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="63093-109">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="63093-110">Los depuradores deben omitir correctamente los tipos de Marcos internos no reconocidos.</span><span class="sxs-lookup"><span data-stu-id="63093-110">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63093-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63093-111">Requirements</span></span>  

 <span data-ttu-id="63093-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63093-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63093-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63093-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63093-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63093-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63093-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63093-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
