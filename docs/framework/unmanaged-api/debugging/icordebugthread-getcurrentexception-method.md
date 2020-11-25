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
ms.openlocfilehash: c21be7b062b7e2d4129bafabae004351442ab853
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728061"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="9133a-102">ICorDebugThread::GetCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="9133a-102">ICorDebugThread::GetCurrentException Method</span></span>

<span data-ttu-id="9133a-103">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que se está iniciando actualmente mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="9133a-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9133a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9133a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9133a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9133a-105">Parameters</span></span>  

 `ppExceptionObject`  
 <span data-ttu-id="9133a-106">enuncia Puntero a la dirección de un `ICorDebugValue` objeto que representa la excepción que el código administrado está produciendo actualmente.</span><span class="sxs-lookup"><span data-stu-id="9133a-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9133a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9133a-107">Remarks</span></span>  

 <span data-ttu-id="9133a-108">El objeto de excepción existirá desde el momento en que se produce la excepción hasta el final del `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="9133a-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="9133a-109">Una evaluación de función, que se realiza mediante los métodos ICorDebugEval, borrará el objeto de excepción en el programa de instalación y lo restaurará cuando se complete.</span><span class="sxs-lookup"><span data-stu-id="9133a-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="9133a-110">Las excepciones se pueden anidar (por ejemplo, si se produce una excepción en un filtro o en una evaluación de función), por lo que puede haber varias excepciones pendientes en un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="9133a-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="9133a-111">`GetCurrentException` Devuelve la excepción más actual.</span><span class="sxs-lookup"><span data-stu-id="9133a-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="9133a-112">El objeto de excepción y el tipo pueden cambiar a lo largo de la duración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="9133a-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="9133a-113">Por ejemplo, después de que se produzca una excepción de tipo x, el Common Language Runtime (CLR) puede quedarse sin memoria y promoverlo a una excepción de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="9133a-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9133a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9133a-114">Requirements</span></span>  

 <span data-ttu-id="9133a-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9133a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9133a-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9133a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9133a-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9133a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9133a-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9133a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
