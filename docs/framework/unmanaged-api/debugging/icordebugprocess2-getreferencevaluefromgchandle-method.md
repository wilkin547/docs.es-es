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
ms.openlocfilehash: 143eefd557511f80007c88c1678143a885377467
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212989"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="4dade-102">ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="4dade-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="4dade-103">Obtiene un puntero de referencia al objeto administrado especificado que tiene un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4dade-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dade-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4dade-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dade-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4dade-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="4dade-106">de Un puntero a un objeto administrado que tiene un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4dade-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="4dade-107">Este valor es un <xref:System.IntPtr> objeto y se puede recuperar de <xref:System.Runtime.InteropServices.GCHandle> para el objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="4dade-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="4dade-108">enuncia Puntero a la dirección de un objeto ICorDebugReferenceValue que representa una referencia al objeto administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="4dade-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dade-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4dade-109">Remarks</span></span>  
 <span data-ttu-id="4dade-110">No confunda el valor de referencia devuelto con un valor de referencia de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4dade-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="4dade-111">La referencia devuelta se comporta como una referencia normal.</span><span class="sxs-lookup"><span data-stu-id="4dade-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="4dade-112">Está deshabilitada cuando la ejecución del código continúa después de un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="4dade-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="4dade-113">La duración del objeto de destino no se ve afectada por la duración del valor de referencia.</span><span class="sxs-lookup"><span data-stu-id="4dade-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4dade-114">El `GetReferenceValueFromGCHandle` método no valida el identificador.</span><span class="sxs-lookup"><span data-stu-id="4dade-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="4dade-115">Por consiguiente, el `GetReferenceValueFromGCHandle` método puede dañar potencialmente el depurador y el código que se está depurando si se pasa un identificador no válido.</span><span class="sxs-lookup"><span data-stu-id="4dade-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dade-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4dade-116">Requirements</span></span>  
 <span data-ttu-id="4dade-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dade-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dade-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4dade-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dade-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dade-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dade-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dade-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
