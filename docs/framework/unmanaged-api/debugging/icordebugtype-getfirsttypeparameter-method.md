---
title: "ICorDebugType::GetFirstTypeParameter (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetFirstTypeParameter
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 233d7165e73c2b568a1693eeab024380bc356d1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="5e615-102">ICorDebugType::GetFirstTypeParameter (Método)</span><span class="sxs-lookup"><span data-stu-id="5e615-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="5e615-103">Obtiene un puntero de interfaz a una instancia de ICorDebugType que representa la primera <xref:System.Type> parámetro del tipo representado por este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="5e615-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e615-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e615-104">Syntax</span></span>  
  
```  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e615-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e615-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="5e615-106">[out] Un puntero a la dirección de un `ICorDebugType` objeto que representa el primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="5e615-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e615-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e615-107">Remarks</span></span>  
 <span data-ttu-id="5e615-108">`GetFirstTypeParameter`puede llamarse en casos donde la información adicional sobre el tipo implica, como máximo, un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="5e615-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="5e615-109">En concreto, se puede utilizar si el tipo es un ELEMENT_TYPE_ARRAY ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR, tal y como indica la [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="5e615-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e615-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e615-110">Requirements</span></span>  
 <span data-ttu-id="5e615-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e615-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e615-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e615-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e615-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e615-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e615-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e615-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
