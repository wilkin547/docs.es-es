---
title: ICorDebugThread::EnumerateChains (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f131f7566376d6474f3189d5eb612b30bec2e2b7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648435"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="fcd41-102">ICorDebugThread::EnumerateChains (Método)</span><span class="sxs-lookup"><span data-stu-id="fcd41-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="fcd41-103">Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum que contiene todas las cadenas de pila en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="fcd41-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd41-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcd41-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcd41-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fcd41-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="fcd41-106">[out] Un puntero a la dirección de un `ICorDebugChainEnum` objeto que permite la enumeración de la pila de todos los encadena en este subproceso, empezando por la cadena activa (es decir, la más reciente).</span><span class="sxs-lookup"><span data-stu-id="fcd41-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcd41-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fcd41-107">Remarks</span></span>  
 <span data-ttu-id="fcd41-108">La cadena de pila representa la pila de llamadas física del subproceso.</span><span class="sxs-lookup"><span data-stu-id="fcd41-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="fcd41-109">Las circunstancias siguientes crean un límite de la cadena de pila:</span><span class="sxs-lookup"><span data-stu-id="fcd41-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="fcd41-110">Una transición de administrado a no administrado o no administrado a administrado.</span><span class="sxs-lookup"><span data-stu-id="fcd41-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="fcd41-111">Un cambio de contexto.</span><span class="sxs-lookup"><span data-stu-id="fcd41-111">A context switch.</span></span>  
  
- <span data-ttu-id="fcd41-112">Un secuestro de un subproceso de usuario del depurador.</span><span class="sxs-lookup"><span data-stu-id="fcd41-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="fcd41-113">En el caso de un subproceso que se ejecuta exclusivamente código administrado en un contexto único, una correspondencia uno a uno existirá entre los subprocesos y las cadenas de la pila.</span><span class="sxs-lookup"><span data-stu-id="fcd41-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="fcd41-114">Un depurador que desee reorganizar las pilas de llamadas física de todos los subprocesos en pilas de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="fcd41-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="fcd41-115">Esto implicaría ordenar las cadenas de todos los subprocesos por sus relaciones de llamador y destinatario y reagrupar ellos.</span><span class="sxs-lookup"><span data-stu-id="fcd41-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd41-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcd41-116">Requirements</span></span>  
 <span data-ttu-id="fcd41-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcd41-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd41-118">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcd41-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcd41-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcd41-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcd41-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd41-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
