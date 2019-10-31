---
title: ICorDebugProcess5::GetTypeFields (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: 0045285a3da22f468c2426bb3b9c4ae7e3e1d7c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132670"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="a68f0-102">ICorDebugProcess5::GetTypeFields (Método)</span><span class="sxs-lookup"><span data-stu-id="a68f0-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="a68f0-103">Proporciona información sobre los campos que pertenecen a un tipo.</span><span class="sxs-lookup"><span data-stu-id="a68f0-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a68f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a68f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a68f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a68f0-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="a68f0-106">de Identificador del tipo cuya información de campo se recupera.</span><span class="sxs-lookup"><span data-stu-id="a68f0-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="a68f0-107">de El número de objetos [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) cuya información de campo se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="a68f0-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="a68f0-108">enuncia Matriz de objetos [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) que proporcionan información sobre los campos que pertenecen al tipo.</span><span class="sxs-lookup"><span data-stu-id="a68f0-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="a68f0-109">enuncia Puntero al número de objetos [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) incluidos en `fields`.</span><span class="sxs-lookup"><span data-stu-id="a68f0-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a68f0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a68f0-110">Remarks</span></span>  
 <span data-ttu-id="a68f0-111">El parámetro `celt`, que especifica el número de campos cuya información de campo utiliza el método para rellenar `fields`, debe corresponder al valor del campo `COR_TYPE_LAYOUT::numFields`.</span><span class="sxs-lookup"><span data-stu-id="a68f0-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a68f0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a68f0-112">Requirements</span></span>  
 <span data-ttu-id="a68f0-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a68f0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a68f0-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a68f0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a68f0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a68f0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a68f0-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a68f0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a68f0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a68f0-117">See also</span></span>

- [<span data-ttu-id="a68f0-118">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a68f0-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="a68f0-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a68f0-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
