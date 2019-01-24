---
title: Método ICorDebugVariableHome::GetArgumentIndex
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 163704bf9a71ceda04bdfd73f9ca676c19d8a62c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526646"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="8c203-102">Método ICorDebugVariableHome::GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="8c203-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="8c203-103">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="8c203-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c203-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c203-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c203-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c203-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="8c203-106">[out] Un puntero en el índice del argumento.</span><span class="sxs-lookup"><span data-stu-id="8c203-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c203-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8c203-107">Return Value</span></span>  
 <span data-ttu-id="8c203-108">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="8c203-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="8c203-109">Valor</span><span class="sxs-lookup"><span data-stu-id="8c203-109">Value</span></span>|<span data-ttu-id="8c203-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c203-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="8c203-111">La llamada al método devolvió un índice de argumento válido.</span><span class="sxs-lookup"><span data-stu-id="8c203-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="8c203-112">Actual [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancia representa una variable local.</span><span class="sxs-lookup"><span data-stu-id="8c203-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c203-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c203-113">Remarks</span></span>  
 <span data-ttu-id="8c203-114">El índice del argumento se puede usar para recuperar metadatos para este argumento.</span><span class="sxs-lookup"><span data-stu-id="8c203-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c203-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c203-115">Requirements</span></span>  
 <span data-ttu-id="8c203-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c203-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c203-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c203-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c203-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c203-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c203-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c203-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c203-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c203-120">See also</span></span>
- [<span data-ttu-id="8c203-121">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c203-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
