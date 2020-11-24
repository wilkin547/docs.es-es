---
title: ICorDebugType::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 1cb9729f175a2e82e88386b0694467c6fe05636a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684465"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="14b81-102">ICorDebugType::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="14b81-102">ICorDebugType::GetClass Method</span></span>

<span data-ttu-id="14b81-103">Obtiene un puntero de interfaz a un ICorDebugClass que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="14b81-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14b81-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14b81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14b81-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14b81-105">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="14b81-106">enuncia Puntero a la dirección de una `ICorDebugClass` interfaz que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="14b81-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14b81-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14b81-107">Remarks</span></span>  

 <span data-ttu-id="14b81-108">`GetClass` solo se puede llamar en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="14b81-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="14b81-109">Llame a [ICorDebugType:: GetType](icordebugtype-gettype-method.md) antes de llamar a `GetClass` .</span><span class="sxs-lookup"><span data-stu-id="14b81-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="14b81-110">Si `ICorDebugType::GetType` devuelve un valor de CorElementType que es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` se puede llamar a para obtener el tipo sin instancia para un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="14b81-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14b81-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14b81-111">Requirements</span></span>  

 <span data-ttu-id="14b81-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14b81-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14b81-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14b81-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14b81-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14b81-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14b81-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14b81-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
