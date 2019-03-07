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
ms.openlocfilehash: 08bf4022f7cd7f85ffe7939c16fd47950e131a77
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471529"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="148b5-102">ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="148b5-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="148b5-103">Obtiene un puntero de referencia al objeto administrado especificado que tiene una colección de elementos no utilizados de identificador.</span><span class="sxs-lookup"><span data-stu-id="148b5-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="148b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="148b5-104">Syntax</span></span>  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="148b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="148b5-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="148b5-106">[in] Un puntero a un objeto administrado que tiene un identificador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="148b5-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="148b5-107">Este valor es un <xref:System.IntPtr> objeto y se pueden recuperar desde el <xref:System.Runtime.InteropServices.GCHandle> para el objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="148b5-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="148b5-108">[out] Un puntero a la dirección de un objeto ICorDebugReferenceValue que representa una referencia al objeto administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="148b5-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="148b5-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="148b5-109">Remarks</span></span>  
 <span data-ttu-id="148b5-110">No confunda el valor devuelto de referencia con un valor de referencia de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="148b5-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="148b5-111">La referencia devuelta se comporta como una referencia normal.</span><span class="sxs-lookup"><span data-stu-id="148b5-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="148b5-112">Se deshabilita cuando la ejecución del código continúa después de un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="148b5-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="148b5-113">La duración del objeto de destino no se ve afectada por la duración del valor de referencia.</span><span class="sxs-lookup"><span data-stu-id="148b5-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="148b5-114">El `GetReferenceValueFromGCHandle` método no valida el identificador.</span><span class="sxs-lookup"><span data-stu-id="148b5-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="148b5-115">Por lo tanto, el `GetReferenceValueFromGCHandle` método puede dañar el depurador y el código que se está depurando si se pasa un identificador no válido.</span><span class="sxs-lookup"><span data-stu-id="148b5-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="148b5-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="148b5-116">Requirements</span></span>  
 <span data-ttu-id="148b5-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="148b5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="148b5-118">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="148b5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="148b5-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="148b5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="148b5-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="148b5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
