---
description: 'Más información acerca de: ICorDebugThread:: Enumeratechains ((método)'
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
ms.openlocfilehash: b9184a1b298e1d29970c5e56ceca76715b0ed096
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659301"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="d20e1-103">ICorDebugThread::EnumerateChains (Método)</span><span class="sxs-lookup"><span data-stu-id="d20e1-103">ICorDebugThread::EnumerateChains Method</span></span>

<span data-ttu-id="d20e1-104">Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de pila de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d20e1-104">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d20e1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d20e1-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d20e1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d20e1-106">Parameters</span></span>  

 `ppChains`  
 <span data-ttu-id="d20e1-107">enuncia Puntero a la dirección de un `ICorDebugChainEnum` objeto que permite la enumeración de todas las cadenas de la pila en este subproceso, a partir de la cadena activa (es decir, la más reciente).</span><span class="sxs-lookup"><span data-stu-id="d20e1-107">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d20e1-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d20e1-108">Remarks</span></span>  

 <span data-ttu-id="d20e1-109">La cadena de pila representa la pila de llamadas física del subproceso.</span><span class="sxs-lookup"><span data-stu-id="d20e1-109">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="d20e1-110">Las siguientes circunstancias crean un límite de cadena de pila:</span><span class="sxs-lookup"><span data-stu-id="d20e1-110">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="d20e1-111">Una transición administrada a no administrada o no administrada.</span><span class="sxs-lookup"><span data-stu-id="d20e1-111">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="d20e1-112">Un cambio de contexto.</span><span class="sxs-lookup"><span data-stu-id="d20e1-112">A context switch.</span></span>  
  
- <span data-ttu-id="d20e1-113">Un depurador que secuestra un subproceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="d20e1-113">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="d20e1-114">En el caso simple de un subproceso que ejecuta código meramente administrado en un contexto único, existirá una correspondencia uno a uno entre los subprocesos y las cadenas de pila.</span><span class="sxs-lookup"><span data-stu-id="d20e1-114">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="d20e1-115">Es posible que un depurador desee reorganizar las pilas de llamadas físicas de todos los subprocesos en pilas de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="d20e1-115">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="d20e1-116">Esto implicaría ordenar todas las cadenas de subprocesos por sus relaciones llamador y destinatario y reagruparlas.</span><span class="sxs-lookup"><span data-stu-id="d20e1-116">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d20e1-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d20e1-117">Requirements</span></span>  

 <span data-ttu-id="d20e1-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d20e1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d20e1-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d20e1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d20e1-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d20e1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d20e1-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d20e1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
