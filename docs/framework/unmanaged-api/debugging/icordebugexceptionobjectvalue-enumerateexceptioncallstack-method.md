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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09f1bc2ae9d56eeb6a6242c32d14bf950684d69d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415618"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="3c70b-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack (Método)</span><span class="sxs-lookup"><span data-stu-id="3c70b-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="3c70b-103">Obtiene un enumerador para la pila de llamadas que se incrustan en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="3c70b-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c70b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c70b-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c70b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c70b-105">Parameters</span></span>  
 <span data-ttu-id="3c70b-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="3c70b-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="3c70b-107">[out] Un puntero a la dirección de un [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) objeto de interfaz que es un enumerador de seguimiento de pila para un objeto de excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="3c70b-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c70b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c70b-108">Remarks</span></span>  
 <span data-ttu-id="3c70b-109">Si no hay información de la pila de llamadas está disponible, el método devuelve `S_OK`, y [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) es un enumerador válido con una longitud de 0.</span><span class="sxs-lookup"><span data-stu-id="3c70b-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="3c70b-110">Si el método no puede recuperar la información de seguimiento de pila, el valor devuelto es `E_FAIL` y no se devuelve ningún enumerador.</span><span class="sxs-lookup"><span data-stu-id="3c70b-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="3c70b-111">El [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) objeto es responsable de descodificación de datos de seguimiento de pila de la `_stackTrace` campo del objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="3c70b-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c70b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c70b-112">Requirements</span></span>  
 <span data-ttu-id="3c70b-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c70b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c70b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c70b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c70b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c70b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c70b-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c70b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c70b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c70b-117">See Also</span></span>  
 [<span data-ttu-id="3c70b-118">ICorDebugExceptionObjectValue (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c70b-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 [<span data-ttu-id="3c70b-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3c70b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
