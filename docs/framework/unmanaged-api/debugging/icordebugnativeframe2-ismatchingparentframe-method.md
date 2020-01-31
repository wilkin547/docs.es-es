---
title: ICorDebugNativeFrame2::IsMatchingParentFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
ms.openlocfilehash: aeaa706ef35413a728f8b254cd325f0bcc83acd1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792714"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="2af46-102">ICorDebugNativeFrame2::IsMatchingParentFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="2af46-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="2af46-103">Determina si el marco especificado es el elemento primario del marco actual.</span><span class="sxs-lookup"><span data-stu-id="2af46-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af46-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2af46-104">Syntax</span></span>  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2af46-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2af46-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="2af46-106">de Puntero al objeto de marco que se desea evaluar para el estado primario.</span><span class="sxs-lookup"><span data-stu-id="2af46-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="2af46-107">[out] `true` si `pPotentialParentFrame` es el elemento primario del marco actual; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2af46-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2af46-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2af46-108">Return Value</span></span>  
 <span data-ttu-id="2af46-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2af46-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2af46-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2af46-110">HRESULT</span></span>|<span data-ttu-id="2af46-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af46-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2af46-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2af46-112">S_OK</span></span>|<span data-ttu-id="2af46-113">El estado primario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2af46-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="2af46-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2af46-114">E_FAIL</span></span>|<span data-ttu-id="2af46-115">No se pudo devolver el estado primario.</span><span class="sxs-lookup"><span data-stu-id="2af46-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="2af46-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2af46-116">E_INVALIDARG</span></span>|<span data-ttu-id="2af46-117">`pPotentialParentFrame` o `pIsParent` es null.</span><span class="sxs-lookup"><span data-stu-id="2af46-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2af46-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2af46-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2af46-119">Notas</span><span class="sxs-lookup"><span data-stu-id="2af46-119">Remarks</span></span>  
 <span data-ttu-id="2af46-120">`IsMatchingParentFrame` devuelve `true` si el objeto de marco que se pasa al método es el elemento primario del objeto de marco en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="2af46-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="2af46-121">Si llama al método en un marco que no es un elemento secundario del marco especificado, devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="2af46-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2af46-122">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2af46-122">Requirements</span></span>  
 <span data-ttu-id="2af46-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2af46-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2af46-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2af46-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2af46-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2af46-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2af46-126">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2af46-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af46-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2af46-127">See also</span></span>

- [<span data-ttu-id="2af46-128">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2af46-128">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="2af46-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2af46-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2af46-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="2af46-130">Debugging</span></span>](index.md)
