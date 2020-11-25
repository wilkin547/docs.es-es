---
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
ms.openlocfilehash: c675ba4b56cecd1990184cd2f0e805250c3dfeb7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724889"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="a5a44-102">ICorDebugInternalFrame::GetFrameType (Método)</span><span class="sxs-lookup"><span data-stu-id="a5a44-102">ICorDebugInternalFrame::GetFrameType Method</span></span>

<span data-ttu-id="a5a44-103">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="a5a44-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5a44-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5a44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5a44-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5a44-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="a5a44-106">enuncia Un puntero a un valor de la enumeración CorDebugInternalFrameType (que indica el tipo de marco interno representado por este `ICorDebugInternalFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="a5a44-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5a44-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5a44-107">Remarks</span></span>  

 <span data-ttu-id="a5a44-108">El tipo de marco interno nunca se STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="a5a44-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="a5a44-109">Los depuradores deben omitir correctamente los tipos de Marcos internos no reconocidos.</span><span class="sxs-lookup"><span data-stu-id="a5a44-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5a44-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5a44-110">Requirements</span></span>  

 <span data-ttu-id="a5a44-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5a44-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5a44-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5a44-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5a44-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5a44-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5a44-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5a44-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
