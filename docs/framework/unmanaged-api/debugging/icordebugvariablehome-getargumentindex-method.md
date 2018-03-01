---
title: "ICorDebugVariableHome::GetArgumentIndex (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 739d4d787858f64871269ea9bd467bc49424fbae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="63cd8-102">ICorDebugVariableHome::GetArgumentIndex (método)</span><span class="sxs-lookup"><span data-stu-id="63cd8-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="63cd8-103">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="63cd8-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63cd8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63cd8-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63cd8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63cd8-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="63cd8-106">[out] Un puntero para el índice del argumento.</span><span class="sxs-lookup"><span data-stu-id="63cd8-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63cd8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63cd8-107">Return Value</span></span>  
 <span data-ttu-id="63cd8-108">El método devuelve los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="63cd8-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="63cd8-109">Valor</span><span class="sxs-lookup"><span data-stu-id="63cd8-109">Value</span></span>|<span data-ttu-id="63cd8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="63cd8-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="63cd8-111">La llamada al método devuelve un índice de argumento válido.</span><span class="sxs-lookup"><span data-stu-id="63cd8-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="63cd8-112">Actual [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancia representa una variable local.</span><span class="sxs-lookup"><span data-stu-id="63cd8-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63cd8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63cd8-113">Remarks</span></span>  
 <span data-ttu-id="63cd8-114">El índice del argumento se puede utilizar para recuperar los metadatos para este argumento.</span><span class="sxs-lookup"><span data-stu-id="63cd8-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63cd8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63cd8-115">Requirements</span></span>  
 <span data-ttu-id="63cd8-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63cd8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63cd8-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63cd8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63cd8-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63cd8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63cd8-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63cd8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63cd8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="63cd8-120">See Also</span></span>  
 [<span data-ttu-id="63cd8-121">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="63cd8-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
