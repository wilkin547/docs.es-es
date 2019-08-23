---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21da325ee58df65ac449464f8292f2ba94d99338
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943295"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="fb6c4-102">ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="fb6c4-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="fb6c4-103">Obtiene un puntero de referencia al objeto administrado especificado que tiene un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb6c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb6c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb6c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb6c4-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="fb6c4-106">de Un puntero a un objeto administrado que tiene un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="fb6c4-107">Este valor es un <xref:System.IntPtr> objeto y se puede recuperar <xref:System.Runtime.InteropServices.GCHandle> de para el objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="fb6c4-108">enuncia Puntero a la dirección de un objeto ICorDebugReferenceValue que representa una referencia al objeto administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb6c4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb6c4-109">Remarks</span></span>  
 <span data-ttu-id="fb6c4-110">No confunda el valor de referencia devuelto con un valor de referencia de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="fb6c4-111">La referencia devuelta se comporta como una referencia normal.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="fb6c4-112">Está deshabilitada cuando la ejecución del código continúa después de un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="fb6c4-113">La duración del objeto de destino no se ve afectada por la duración del valor de referencia.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb6c4-114">El `GetReferenceValueFromGCHandle` método no valida el identificador.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="fb6c4-115">Por consiguiente, `GetReferenceValueFromGCHandle` el método puede dañar potencialmente el depurador y el código que se está depurando si se pasa un identificador no válido.</span><span class="sxs-lookup"><span data-stu-id="fb6c4-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb6c4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb6c4-116">Requirements</span></span>  
 <span data-ttu-id="fb6c4-117">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb6c4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb6c4-118">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="fb6c4-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb6c4-119">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb6c4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb6c4-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb6c4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
