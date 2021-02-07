---
description: 'Más información sobre: Icordebugexceptionobjectvalue (:: Enumerateexceptioncallstack ((método)'
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: 97918d280299fae16eb55185baee19c27d99005b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693283"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="ccb2a-103">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack (Método)</span><span class="sxs-lookup"><span data-stu-id="ccb2a-103">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>

<span data-ttu-id="ccb2a-104">Obtiene un enumerador para la pila de llamadas incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-104">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb2a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccb2a-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccb2a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccb2a-106">Parameters</span></span>  

 <span data-ttu-id="ccb2a-107">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="ccb2a-107">ppCallStackEnum</span></span>  
 <span data-ttu-id="ccb2a-108">enuncia Un puntero a la dirección de un objeto de interfaz [icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md) que es un enumerador de seguimiento de pila para un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-108">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccb2a-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ccb2a-109">Remarks</span></span>  

 <span data-ttu-id="ccb2a-110">Si no hay información disponible sobre la pila de llamadas, el método devuelve `S_OK` y [icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md) es un enumerador válido con una longitud de 0.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-110">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="ccb2a-111">Si el método no puede recuperar la información de seguimiento de la pila, el valor devuelto es `E_FAIL` y no se devuelve ningún enumerador.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-111">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="ccb2a-112">El objeto [icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md) es responsable de descodificar los datos de seguimiento de la pila del `_stackTrace` campo del objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="ccb2a-112">The [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccb2a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccb2a-113">Requirements</span></span>  

 <span data-ttu-id="ccb2a-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccb2a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccb2a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ccb2a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccb2a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccb2a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccb2a-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccb2a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb2a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccb2a-118">See also</span></span>

- [<span data-ttu-id="ccb2a-119">ICorDebugExceptionObjectValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccb2a-119">ICorDebugExceptionObjectValue Interface</span></span>](icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="ccb2a-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ccb2a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
