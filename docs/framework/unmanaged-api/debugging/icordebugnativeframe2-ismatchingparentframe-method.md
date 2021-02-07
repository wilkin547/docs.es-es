---
description: 'Más información sobre: ICorDebugNativeFrame2:: Ismatchingparentframe ((método)'
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
ms.openlocfilehash: 6dff1cb7f5205ad742ac4b886f72938dd28bd88f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722209"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="316e4-103">ICorDebugNativeFrame2::IsMatchingParentFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="316e4-103">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>

<span data-ttu-id="316e4-104">Determina si el marco especificado es el elemento primario del marco actual.</span><span class="sxs-lookup"><span data-stu-id="316e4-104">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="316e4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="316e4-105">Syntax</span></span>  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="316e4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="316e4-106">Parameters</span></span>  

 `pPotentialParentFrame`  
 <span data-ttu-id="316e4-107">de Puntero al objeto de marco que se desea evaluar para el estado primario.</span><span class="sxs-lookup"><span data-stu-id="316e4-107">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="316e4-108">[out] `true` `pPotentialParentFrame` es si es el elemento primario del marco actual; en caso contrario, es `false` .</span><span class="sxs-lookup"><span data-stu-id="316e4-108">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="316e4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="316e4-109">Return Value</span></span>  

 <span data-ttu-id="316e4-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="316e4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="316e4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="316e4-111">HRESULT</span></span>|<span data-ttu-id="316e4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="316e4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="316e4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="316e4-113">S_OK</span></span>|<span data-ttu-id="316e4-114">El estado primario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="316e4-114">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="316e4-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="316e4-115">E_FAIL</span></span>|<span data-ttu-id="316e4-116">No se pudo devolver el estado primario.</span><span class="sxs-lookup"><span data-stu-id="316e4-116">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="316e4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="316e4-117">E_INVALIDARG</span></span>|<span data-ttu-id="316e4-118">`pPotentialParentFrame` o `pIsParent` es null.</span><span class="sxs-lookup"><span data-stu-id="316e4-118">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="316e4-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="316e4-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="316e4-120">Notas</span><span class="sxs-lookup"><span data-stu-id="316e4-120">Remarks</span></span>  

 <span data-ttu-id="316e4-121">`IsMatchingParentFrame` Devuelve `true` si el objeto de marco que se pasa al método es el elemento primario del objeto de marco en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="316e4-121">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="316e4-122">Si llama al método en un marco que no es un elemento secundario del marco especificado, devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="316e4-122">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="316e4-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="316e4-123">Requirements</span></span>  

 <span data-ttu-id="316e4-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="316e4-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="316e4-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="316e4-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="316e4-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="316e4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="316e4-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="316e4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="316e4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="316e4-128">See also</span></span>

- [<span data-ttu-id="316e4-129">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="316e4-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="316e4-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="316e4-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="316e4-131">Depuración</span><span class="sxs-lookup"><span data-stu-id="316e4-131">Debugging</span></span>](index.md)
