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
ms.openlocfilehash: 711fccd65379bc3e5e178869e7220dd84fd07fbe
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379701"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="5a198-102">ICorDebugThread::EnumerateChains (Método)</span><span class="sxs-lookup"><span data-stu-id="5a198-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="5a198-103">Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de pila de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="5a198-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a198-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a198-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a198-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a198-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="5a198-106">enuncia Puntero a la dirección de un `ICorDebugChainEnum` objeto que permite la enumeración de todas las cadenas de la pila en este subproceso, a partir de la cadena activa (es decir, la más reciente).</span><span class="sxs-lookup"><span data-stu-id="5a198-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a198-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a198-107">Remarks</span></span>  
 <span data-ttu-id="5a198-108">La cadena de pila representa la pila de llamadas física del subproceso.</span><span class="sxs-lookup"><span data-stu-id="5a198-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="5a198-109">Las siguientes circunstancias crean un límite de cadena de pila:</span><span class="sxs-lookup"><span data-stu-id="5a198-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="5a198-110">Una transición administrada a no administrada o no administrada.</span><span class="sxs-lookup"><span data-stu-id="5a198-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="5a198-111">Un cambio de contexto.</span><span class="sxs-lookup"><span data-stu-id="5a198-111">A context switch.</span></span>  
  
- <span data-ttu-id="5a198-112">Un depurador que secuestra un subproceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="5a198-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="5a198-113">En el caso simple de un subproceso que ejecuta código meramente administrado en un contexto único, existirá una correspondencia uno a uno entre los subprocesos y las cadenas de pila.</span><span class="sxs-lookup"><span data-stu-id="5a198-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="5a198-114">Es posible que un depurador desee reorganizar las pilas de llamadas físicas de todos los subprocesos en pilas de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="5a198-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="5a198-115">Esto implicaría ordenar todas las cadenas de subprocesos por sus relaciones llamador y destinatario y reagruparlas.</span><span class="sxs-lookup"><span data-stu-id="5a198-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a198-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a198-116">Requirements</span></span>  
 <span data-ttu-id="5a198-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a198-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a198-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a198-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a198-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a198-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a198-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a198-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
