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
ms.openlocfilehash: ac42c6254182ea775377a448a54d527b234c97dc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379927"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="f01b4-102">ICorDebugType::GetType (Método)</span><span class="sxs-lookup"><span data-stu-id="f01b4-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="f01b4-103">Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime (CLR) <xref:System.Type> representado por esta ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="f01b4-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f01b4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f01b4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f01b4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f01b4-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="f01b4-106">enuncia Un puntero a un valor de la `CorElementType` enumeración que indica el CLR <xref:System.Type> que este `ICorDebugType` representa.</span><span class="sxs-lookup"><span data-stu-id="f01b4-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f01b4-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f01b4-107">Remarks</span></span>  
 <span data-ttu-id="f01b4-108">Si el valor de `ty` es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, se puede llamar al método [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) para obtener el tipo sin instancia de un tipo genérico; de lo contrario, no se llama a `ICorDebugType::GetClass` .</span><span class="sxs-lookup"><span data-stu-id="f01b4-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f01b4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f01b4-109">Requirements</span></span>  
 <span data-ttu-id="f01b4-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f01b4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f01b4-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f01b4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f01b4-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f01b4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f01b4-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f01b4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
