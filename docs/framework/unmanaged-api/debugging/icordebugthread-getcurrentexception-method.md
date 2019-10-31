---
title: ICorDebugThread::GetCurrentException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
ms.openlocfilehash: 8082b2a3654f1605f18f3b68f54464dc83c8e60a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133490"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="f0ab4-102">ICorDebugThread::GetCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="f0ab4-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="f0ab4-103">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que se está iniciando actualmente mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ab4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0ab4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0ab4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0ab4-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="f0ab4-106">enuncia Puntero a la dirección de un objeto `ICorDebugValue` que representa la excepción que se está iniciando actualmente mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0ab4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f0ab4-107">Remarks</span></span>  
 <span data-ttu-id="f0ab4-108">El objeto de excepción existirá desde el momento en que se produce la excepción hasta el final del bloque de `catch`.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="f0ab4-109">Una evaluación de función, que se realiza mediante los métodos ICorDebugEval, borrará el objeto de excepción en el programa de instalación y lo restaurará cuando se complete.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="f0ab4-110">Las excepciones se pueden anidar (por ejemplo, si se produce una excepción en un filtro o en una evaluación de función), por lo que puede haber varias excepciones pendientes en un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="f0ab4-111">`GetCurrentException` devuelve la excepción más reciente.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="f0ab4-112">El objeto de excepción y el tipo pueden cambiar a lo largo de la duración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="f0ab4-113">Por ejemplo, después de que se produzca una excepción de tipo x, el Common Language Runtime (CLR) puede quedarse sin memoria y promoverlo a una excepción de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="f0ab4-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0ab4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0ab4-114">Requirements</span></span>  
 <span data-ttu-id="f0ab4-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0ab4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0ab4-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0ab4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0ab4-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0ab4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0ab4-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0ab4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
