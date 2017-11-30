---
title: "ICorDebugType::GetClass (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be9999cd0dd8db5439dd41e51429841666597b16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="2c1e6-102">ICorDebugType::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="2c1e6-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="2c1e6-103">Obtiene un puntero de interfaz a un ICorDebugClass que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="2c1e6-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c1e6-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c1e6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c1e6-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="2c1e6-106">[out] Un puntero a la dirección de un `ICorDebugClass` interfaz que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="2c1e6-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c1e6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c1e6-107">Remarks</span></span>  
 <span data-ttu-id="2c1e6-108">`GetClass`se puede llamar únicamente bajo ciertas condiciones.</span><span class="sxs-lookup"><span data-stu-id="2c1e6-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="2c1e6-109">Llame a [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) antes de llamar a `GetClass`.</span><span class="sxs-lookup"><span data-stu-id="2c1e6-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="2c1e6-110">Si `ICorDebugType::GetType` devuelve un valor de CorElementType es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` se puede llamar para obtener el tipo sin instancias de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="2c1e6-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c1e6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c1e6-111">Requirements</span></span>  
 <span data-ttu-id="2c1e6-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c1e6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c1e6-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c1e6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c1e6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c1e6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c1e6-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c1e6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
