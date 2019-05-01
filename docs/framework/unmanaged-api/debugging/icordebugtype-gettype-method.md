---
title: ICorDebugType::GetType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6b36c524921a4fecf8bc5ddcbace62af6450b6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993907"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="36d86-102">ICorDebugType::GetType (Método)</span><span class="sxs-lookup"><span data-stu-id="36d86-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="36d86-103">Obtiene un valor de CorElementType que describe el tipo nativo de common language runtime (CLR) <xref:System.Type> representado por esta instancia de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="36d86-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36d86-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36d86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36d86-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="36d86-106">[out] Un puntero a un valor de la `CorElementType` enumeración que indica el CLR <xref:System.Type> que `ICorDebugType` representa.</span><span class="sxs-lookup"><span data-stu-id="36d86-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36d86-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36d86-107">Remarks</span></span>  
 <span data-ttu-id="36d86-108">Si el valor de `ty` es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, el [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) método puede llamarse para obtener el tipo sin instancias de un tipo genérico; de lo contrario, no llame a `ICorDebugType::GetClass`.</span><span class="sxs-lookup"><span data-stu-id="36d86-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36d86-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36d86-109">Requirements</span></span>  
 <span data-ttu-id="36d86-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36d86-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36d86-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36d86-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36d86-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36d86-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36d86-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36d86-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
