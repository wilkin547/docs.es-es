---
description: 'Más información acerca de: ICorDebugType:: GetClass (método)'
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
ms.openlocfilehash: 2e8d68fbc8909599ca649ba0e226cc84af820939
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658352"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="e5705-103">ICorDebugType::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="e5705-103">ICorDebugType::GetClass Method</span></span>

<span data-ttu-id="e5705-104">Obtiene un puntero de interfaz a un ICorDebugClass que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="e5705-104">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5705-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5705-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5705-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5705-106">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="e5705-107">enuncia Puntero a la dirección de una `ICorDebugClass` interfaz que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="e5705-107">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5705-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5705-108">Remarks</span></span>  

 <span data-ttu-id="e5705-109">`GetClass` solo se puede llamar en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="e5705-109">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="e5705-110">Llame a [ICorDebugType:: GetType](icordebugtype-gettype-method.md) antes de llamar a `GetClass` .</span><span class="sxs-lookup"><span data-stu-id="e5705-110">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="e5705-111">Si `ICorDebugType::GetType` devuelve un valor de CorElementType que es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` se puede llamar a para obtener el tipo sin instancia para un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="e5705-111">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5705-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5705-112">Requirements</span></span>  

 <span data-ttu-id="e5705-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5705-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5705-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5705-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5705-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5705-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5705-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5705-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
