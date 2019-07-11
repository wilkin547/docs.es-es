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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a5461cc6a78347cdbe0d0b13f8111cb24c11006
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760045"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="cd6b6-102">ICorDebugInternalFrame::GetFrameType (Método)</span><span class="sxs-lookup"><span data-stu-id="cd6b6-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="cd6b6-103">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="cd6b6-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd6b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd6b6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd6b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd6b6-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="cd6b6-106">[out] Un puntero a un valor de la enumeración CorDebugInternalFrameType que indica el tipo de marco interno representado por este `ICorDebugInternalFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="cd6b6-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd6b6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd6b6-107">Remarks</span></span>  
 <span data-ttu-id="cd6b6-108">El tipo de marco interno nunca será STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="cd6b6-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="cd6b6-109">Los depuradores deberían omitir correctamente los tipos de marco interno no reconocido.</span><span class="sxs-lookup"><span data-stu-id="cd6b6-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd6b6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd6b6-110">Requirements</span></span>  
 <span data-ttu-id="cd6b6-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd6b6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd6b6-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd6b6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd6b6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd6b6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd6b6-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd6b6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
