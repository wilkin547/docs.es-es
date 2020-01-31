---
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
ms.openlocfilehash: 57eb284bfe39ce92b2d6c03a2aeb4ae84d6aba91
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788673"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="d2641-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack (Método)</span><span class="sxs-lookup"><span data-stu-id="d2641-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="d2641-103">Obtiene un enumerador para la pila de llamadas incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="d2641-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2641-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2641-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2641-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d2641-105">Parameters</span></span>  
 <span data-ttu-id="d2641-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="d2641-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="d2641-107">enuncia Un puntero a la dirección de un objeto de interfaz [icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md) que es un enumerador de seguimiento de pila para un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="d2641-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2641-108">Notas</span><span class="sxs-lookup"><span data-stu-id="d2641-108">Remarks</span></span>  
 <span data-ttu-id="d2641-109">Si no hay información disponible sobre la pila de llamadas, el método devuelve `S_OK`y [icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md) es un enumerador válido con una longitud de 0.</span><span class="sxs-lookup"><span data-stu-id="d2641-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="d2641-110">Si el método no puede recuperar la información de seguimiento de la pila, el valor devuelto es `E_FAIL` y no se devuelve ningún enumerador.</span><span class="sxs-lookup"><span data-stu-id="d2641-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="d2641-111">El objeto [icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md) es responsable de descodificar los datos de seguimiento de la pila del campo `_stackTrace` del objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="d2641-111">The [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2641-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d2641-112">Requirements</span></span>  
 <span data-ttu-id="d2641-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2641-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2641-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2641-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2641-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2641-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2641-116">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2641-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2641-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2641-117">See also</span></span>

- [<span data-ttu-id="d2641-118">ICorDebugExceptionObjectValue (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2641-118">ICorDebugExceptionObjectValue Interface</span></span>](icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="d2641-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d2641-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
