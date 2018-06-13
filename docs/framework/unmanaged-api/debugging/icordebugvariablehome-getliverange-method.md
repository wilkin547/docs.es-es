---
title: IcorDebugVariableHome::GetLiveRange (método)
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0f9c586a9e95fc2e57c4956601f6dce2b988159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423070"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="1727c-102">IcorDebugVariableHome::GetLiveRange (método)</span><span class="sxs-lookup"><span data-stu-id="1727c-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="1727c-103">Obtiene el rango nativo durante el cual esta variable es en vivo.</span><span class="sxs-lookup"><span data-stu-id="1727c-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1727c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1727c-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1727c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1727c-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="1727c-106">[out] El desplazamiento lógico en el que la variable es el primera en vivo.</span><span class="sxs-lookup"><span data-stu-id="1727c-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="1727c-107">[out] El desplazamiento lógico inmediatamente después del punto en el que la variable es el última en vivo.</span><span class="sxs-lookup"><span data-stu-id="1727c-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1727c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1727c-108">Requirements</span></span>  
 <span data-ttu-id="1727c-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1727c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1727c-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1727c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1727c-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1727c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1727c-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1727c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1727c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1727c-113">See Also</span></span>  
 [<span data-ttu-id="1727c-114">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1727c-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
