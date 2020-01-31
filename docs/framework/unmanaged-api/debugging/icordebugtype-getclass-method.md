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
ms.openlocfilehash: d403a8bfba3599a60d8af72307590f5a569480dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791296"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="4bc69-102">ICorDebugType::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="4bc69-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="4bc69-103">Obtiene un puntero de interfaz a un ICorDebugClass que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="4bc69-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bc69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bc69-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bc69-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4bc69-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="4bc69-106">enuncia Puntero a la dirección de una interfaz `ICorDebugClass` que representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="4bc69-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bc69-107">Notas</span><span class="sxs-lookup"><span data-stu-id="4bc69-107">Remarks</span></span>  
 <span data-ttu-id="4bc69-108">solo se puede llamar a `GetClass` en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="4bc69-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="4bc69-109">Llame a [ICorDebugType:: GetType](icordebugtype-gettype-method.md) antes de llamar a `GetClass`.</span><span class="sxs-lookup"><span data-stu-id="4bc69-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="4bc69-110">Si `ICorDebugType::GetType` devuelve un valor de CorElementType que es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, se puede llamar a `GetClass` para obtener el tipo sin instancia para un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="4bc69-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bc69-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4bc69-111">Requirements</span></span>  
 <span data-ttu-id="4bc69-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bc69-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bc69-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bc69-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bc69-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bc69-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bc69-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bc69-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
