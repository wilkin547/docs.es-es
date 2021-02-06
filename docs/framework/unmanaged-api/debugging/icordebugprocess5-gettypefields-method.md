---
description: 'Más información sobre: ICorDebugProcess5:: Gettypefields ((método)'
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
ms.openlocfilehash: bdbb0be76400262d83876b9fc37cc4f00eb34e43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649824"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="82dda-103">ICorDebugProcess5::GetTypeFields (Método)</span><span class="sxs-lookup"><span data-stu-id="82dda-103">ICorDebugProcess5::GetTypeFields Method</span></span>

<span data-ttu-id="82dda-104">Proporciona información sobre los campos que pertenecen a un tipo.</span><span class="sxs-lookup"><span data-stu-id="82dda-104">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82dda-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82dda-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82dda-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82dda-106">Parameters</span></span>  

 `id`  
 <span data-ttu-id="82dda-107">de Identificador del tipo cuya información de campo se recupera.</span><span class="sxs-lookup"><span data-stu-id="82dda-107">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="82dda-108">de El número de objetos de [COR_FIELD](cor-field-structure.md) cuya información de campo se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="82dda-108">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="82dda-109">enuncia Matriz de objetos [COR_FIELD](cor-field-structure.md) que proporcionan información sobre los campos que pertenecen al tipo.</span><span class="sxs-lookup"><span data-stu-id="82dda-109">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="82dda-110">enuncia Puntero al número de objetos [COR_FIELD](cor-field-structure.md) incluidos en `fields` .</span><span class="sxs-lookup"><span data-stu-id="82dda-110">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82dda-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="82dda-111">Remarks</span></span>  

 <span data-ttu-id="82dda-112">El `celt` parámetro, que especifica el número de campos cuya información de campo utiliza el método para rellenar `fields` , debe corresponderse con el valor del `COR_TYPE_LAYOUT::numFields` campo.</span><span class="sxs-lookup"><span data-stu-id="82dda-112">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82dda-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82dda-113">Requirements</span></span>  

 <span data-ttu-id="82dda-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82dda-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82dda-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82dda-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82dda-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82dda-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82dda-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82dda-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82dda-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="82dda-118">See also</span></span>

- [<span data-ttu-id="82dda-119">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82dda-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="82dda-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="82dda-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
