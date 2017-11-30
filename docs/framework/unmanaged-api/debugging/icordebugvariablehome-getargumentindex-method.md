---
title: "ICorDebugVariableHome::GetArgumentIndex (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetArgumentIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 175e45758d26d8168279c825d41ee58d049edf0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="e7aff-102">ICorDebugVariableHome::GetArgumentIndex (método)</span><span class="sxs-lookup"><span data-stu-id="e7aff-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="e7aff-103">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="e7aff-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7aff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7aff-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7aff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7aff-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="e7aff-106">[out] Un puntero para el índice del argumento.</span><span class="sxs-lookup"><span data-stu-id="e7aff-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7aff-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e7aff-107">Return Value</span></span>  
 <span data-ttu-id="e7aff-108">El método devuelve los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="e7aff-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="e7aff-109">Valor</span><span class="sxs-lookup"><span data-stu-id="e7aff-109">Value</span></span>|<span data-ttu-id="e7aff-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7aff-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="e7aff-111">La llamada al método devuelve un índice de argumento válido.</span><span class="sxs-lookup"><span data-stu-id="e7aff-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="e7aff-112">Actual [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancia representa una variable local.</span><span class="sxs-lookup"><span data-stu-id="e7aff-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7aff-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7aff-113">Remarks</span></span>  
 <span data-ttu-id="e7aff-114">El índice del argumento se puede utilizar para recuperar los metadatos para este argumento.</span><span class="sxs-lookup"><span data-stu-id="e7aff-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7aff-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7aff-115">Requirements</span></span>  
 <span data-ttu-id="e7aff-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7aff-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7aff-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7aff-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7aff-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7aff-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7aff-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7aff-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7aff-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7aff-120">See Also</span></span>  
 [<span data-ttu-id="e7aff-121">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="e7aff-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
