---
title: "ICorDebugThread::EnumerateChains (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e6a9637edb4a846b4d10dd6565533a9219ad558
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="d8bd7-102">ICorDebugThread::EnumerateChains (Método)</span><span class="sxs-lookup"><span data-stu-id="d8bd7-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="d8bd7-103">Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum que contiene todas las cadenas de pila en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d8bd7-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8bd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8bd7-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8bd7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8bd7-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="d8bd7-106">[out] Un puntero a la dirección de un `ICorDebugChainEnum` vincula el objeto que permite la enumeración de todos los del pila en este subproceso, empezando por la cadena de activo (es decir, la más reciente).</span><span class="sxs-lookup"><span data-stu-id="d8bd7-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8bd7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8bd7-107">Remarks</span></span>  
 <span data-ttu-id="d8bd7-108">La cadena de pila representa la pila de llamadas física del subproceso.</span><span class="sxs-lookup"><span data-stu-id="d8bd7-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="d8bd7-109">Las circunstancias siguientes crean un límite de la cadena de pila:</span><span class="sxs-lookup"><span data-stu-id="d8bd7-109">The following circumstances create a stack chain boundary:</span></span>  
  
-   <span data-ttu-id="d8bd7-110">Una transición a administrado o no administrado a administrado.</span><span class="sxs-lookup"><span data-stu-id="d8bd7-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
-   <span data-ttu-id="d8bd7-111">Un cambio de contexto.</span><span class="sxs-lookup"><span data-stu-id="d8bd7-111">A context switch.</span></span>  
  
-   <span data-ttu-id="d8bd7-112">Un secuestro de un subproceso de usuario del depurador.</span><span class="sxs-lookup"><span data-stu-id="d8bd7-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="d8bd7-113">En un caso simple para un subproceso que se ejecuta exclusivamente código administrado en un único contexto, existirá una correspondencia uno a uno entre los subprocesos y cadenas de la pila.</span><span class="sxs-lookup"><span data-stu-id="d8bd7-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="d8bd7-114">Un depurador que desee reorganizar las pilas de llamadas física de todos los subprocesos en pilas de llamada lógico.</span><span class="sxs-lookup"><span data-stu-id="d8bd7-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="d8bd7-115">Esto incluiría la ordenación de cadenas de todos los subprocesos por sus relaciones de llamador/destinatario y reagrupar ellos.</span><span class="sxs-lookup"><span data-stu-id="d8bd7-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8bd7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8bd7-116">Requirements</span></span>  
 <span data-ttu-id="d8bd7-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8bd7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8bd7-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8bd7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8bd7-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8bd7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8bd7-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8bd7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
