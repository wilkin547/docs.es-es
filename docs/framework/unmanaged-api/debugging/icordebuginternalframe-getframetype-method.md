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
ms.openlocfilehash: 3f7e5fceacc3fefa9267a9d7f989e745c392322e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414130"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="3ea20-102">ICorDebugInternalFrame::GetFrameType (Método)</span><span class="sxs-lookup"><span data-stu-id="3ea20-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="3ea20-103">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="3ea20-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ea20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ea20-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ea20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ea20-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="3ea20-106">[out] Un puntero a un valor de la enumeración CorDebugInternalFrameType que indica el tipo de marco interno representado por este `ICorDebugInternalFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="3ea20-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ea20-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ea20-107">Remarks</span></span>  
 <span data-ttu-id="3ea20-108">El tipo de marco interno nunca será STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="3ea20-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="3ea20-109">Depuradores deberían omitir correctamente los tipos de marco internos no reconocidos.</span><span class="sxs-lookup"><span data-stu-id="3ea20-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ea20-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ea20-110">Requirements</span></span>  
 <span data-ttu-id="3ea20-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ea20-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ea20-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ea20-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ea20-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ea20-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ea20-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ea20-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
