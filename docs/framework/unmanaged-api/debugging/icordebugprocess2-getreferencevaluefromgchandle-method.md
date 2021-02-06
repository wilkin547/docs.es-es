---
description: 'Más información sobre: ICorDebugProcess2:: Getreferencevaluefromgchandle ((método)'
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
ms.openlocfilehash: 02047dee9116d34a365242f2a532766eb60e1c81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650246"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="c4259-103">ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="c4259-103">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>

<span data-ttu-id="c4259-104">Obtiene un puntero de referencia al objeto administrado especificado que tiene un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c4259-104">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4259-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4259-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4259-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4259-106">Parameters</span></span>  

 `handle`  
 <span data-ttu-id="c4259-107">de Un puntero a un objeto administrado que tiene un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c4259-107">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="c4259-108">Este valor es un <xref:System.IntPtr> objeto y se puede recuperar de <xref:System.Runtime.InteropServices.GCHandle> para el objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="c4259-108">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="c4259-109">enuncia Puntero a la dirección de un objeto ICorDebugReferenceValue que representa una referencia al objeto administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="c4259-109">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4259-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c4259-110">Remarks</span></span>  

 <span data-ttu-id="c4259-111">No confunda el valor de referencia devuelto con un valor de referencia de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c4259-111">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="c4259-112">La referencia devuelta se comporta como una referencia normal.</span><span class="sxs-lookup"><span data-stu-id="c4259-112">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="c4259-113">Está deshabilitada cuando la ejecución del código continúa después de un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="c4259-113">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="c4259-114">La duración del objeto de destino no se ve afectada por la duración del valor de referencia.</span><span class="sxs-lookup"><span data-stu-id="c4259-114">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4259-115">El `GetReferenceValueFromGCHandle` método no valida el identificador.</span><span class="sxs-lookup"><span data-stu-id="c4259-115">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="c4259-116">Por consiguiente, el `GetReferenceValueFromGCHandle` método puede dañar potencialmente el depurador y el código que se está depurando si se pasa un identificador no válido.</span><span class="sxs-lookup"><span data-stu-id="c4259-116">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4259-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4259-117">Requirements</span></span>  

 <span data-ttu-id="c4259-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4259-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4259-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4259-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4259-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4259-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4259-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4259-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
