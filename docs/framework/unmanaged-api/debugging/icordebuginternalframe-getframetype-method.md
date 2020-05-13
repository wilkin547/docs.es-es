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
ms.openlocfilehash: 6b598352f734cf47514a82de1d0fca65d430a9ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209973"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="710c5-102">ICorDebugInternalFrame::GetFrameType (Método)</span><span class="sxs-lookup"><span data-stu-id="710c5-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="710c5-103">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="710c5-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="710c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="710c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="710c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="710c5-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="710c5-106">enuncia Un puntero a un valor de la enumeración CorDebugInternalFrameType (que indica el tipo de marco interno representado por este `ICorDebugInternalFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="710c5-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="710c5-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="710c5-107">Remarks</span></span>  
 <span data-ttu-id="710c5-108">El tipo de marco interno nunca se STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="710c5-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="710c5-109">Los depuradores deben omitir correctamente los tipos de Marcos internos no reconocidos.</span><span class="sxs-lookup"><span data-stu-id="710c5-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="710c5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="710c5-110">Requirements</span></span>  
 <span data-ttu-id="710c5-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="710c5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="710c5-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="710c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="710c5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="710c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="710c5-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="710c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
