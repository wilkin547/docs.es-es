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
ms.openlocfilehash: 878a57514af34730049864f17f4853c1237904c2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379958"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="901b2-102">ICorDebugType::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="901b2-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="901b2-103">Obtiene un puntero de interfaz a un ICorDebugClass que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="901b2-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="901b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="901b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="901b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="901b2-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="901b2-106">enuncia Puntero a la dirección de una `ICorDebugClass` interfaz que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="901b2-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="901b2-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="901b2-107">Remarks</span></span>  
 <span data-ttu-id="901b2-108">`GetClass`solo se puede llamar en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="901b2-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="901b2-109">Llame a [ICorDebugType:: GetType](icordebugtype-gettype-method.md) antes de llamar a `GetClass` .</span><span class="sxs-lookup"><span data-stu-id="901b2-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="901b2-110">Si `ICorDebugType::GetType` devuelve un valor de CorElementType que es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` se puede llamar a para obtener el tipo sin instancia para un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="901b2-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="901b2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="901b2-111">Requirements</span></span>  
 <span data-ttu-id="901b2-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="901b2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="901b2-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="901b2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="901b2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="901b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="901b2-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="901b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
