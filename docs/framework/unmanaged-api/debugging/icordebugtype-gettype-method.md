---
description: 'Más información acerca de: ICorDebugType:: GetType (método)'
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
ms.openlocfilehash: 922791e51855badfb1fd548e08953a2f660f971a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658222"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="7c649-103">ICorDebugType::GetType (Método)</span><span class="sxs-lookup"><span data-stu-id="7c649-103">ICorDebugType::GetType Method</span></span>

<span data-ttu-id="7c649-104">Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime (CLR) <xref:System.Type> representado por esta ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="7c649-104">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c649-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c649-105">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c649-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c649-106">Parameters</span></span>  

 `ty`  
 <span data-ttu-id="7c649-107">enuncia Un puntero a un valor de la `CorElementType` enumeración que indica el CLR <xref:System.Type> que este `ICorDebugType` representa.</span><span class="sxs-lookup"><span data-stu-id="7c649-107">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c649-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7c649-108">Remarks</span></span>  

 <span data-ttu-id="7c649-109">Si el valor de `ty` es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, se puede llamar al método [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) para obtener el tipo sin instancia de un tipo genérico; de lo contrario, no se llama a `ICorDebugType::GetClass` .</span><span class="sxs-lookup"><span data-stu-id="7c649-109">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c649-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c649-110">Requirements</span></span>  

 <span data-ttu-id="7c649-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c649-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c649-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c649-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c649-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c649-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c649-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c649-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
