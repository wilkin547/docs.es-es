---
title: Método IcorDebugVariableHome::GetLiveRange
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
ms.openlocfilehash: 7e2c9e981f431bb87df61a71389abf3d42a6a507
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123817"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="a3503-102">Método IcorDebugVariableHome::GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="a3503-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="a3503-103">Obtiene el intervalo nativo a través de la que esta variable está activa.</span><span class="sxs-lookup"><span data-stu-id="a3503-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3503-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3503-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3503-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3503-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="a3503-106">[out] El desplazamiento lógico en el que la variable es el primera en vivo.</span><span class="sxs-lookup"><span data-stu-id="a3503-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="a3503-107">[out] El desplazamiento lógico inmediatamente después del punto en el que la variable es el última en vivo.</span><span class="sxs-lookup"><span data-stu-id="a3503-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3503-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3503-108">Requirements</span></span>  
 <span data-ttu-id="a3503-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3503-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3503-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3503-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3503-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3503-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a3503-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a3503-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a3503-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3503-113">See also</span></span>

- [<span data-ttu-id="a3503-114">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="a3503-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
