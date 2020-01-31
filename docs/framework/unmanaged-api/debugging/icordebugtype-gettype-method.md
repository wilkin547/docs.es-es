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
ms.openlocfilehash: 25ffbf73fbefbb3c584450283c3080dfc11ee598
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791239"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="fa87f-102">ICorDebugType::GetType (Método)</span><span class="sxs-lookup"><span data-stu-id="fa87f-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="fa87f-103">Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime (CLR) <xref:System.Type> representado por esta ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="fa87f-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa87f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa87f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa87f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="fa87f-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="fa87f-106">enuncia Un puntero a un valor de la enumeración `CorElementType` que indica el <xref:System.Type> CLR que este `ICorDebugType` representa.</span><span class="sxs-lookup"><span data-stu-id="fa87f-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa87f-107">Notas</span><span class="sxs-lookup"><span data-stu-id="fa87f-107">Remarks</span></span>  
 <span data-ttu-id="fa87f-108">Si el valor de `ty` es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, se puede llamar al método [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) para obtener el tipo sin instancia de un tipo genérico; de lo contrario, no llame a `ICorDebugType::GetClass`.</span><span class="sxs-lookup"><span data-stu-id="fa87f-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa87f-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="fa87f-109">Requirements</span></span>  
 <span data-ttu-id="fa87f-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa87f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa87f-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa87f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa87f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa87f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa87f-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa87f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
