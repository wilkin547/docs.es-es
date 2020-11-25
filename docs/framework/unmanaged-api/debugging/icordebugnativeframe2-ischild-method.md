---
title: ICorDebugNativeFrame2::IsChild (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
ms.openlocfilehash: 0d65849aba08c7d143a6977e7dfb8cff85274a64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695574"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="2373b-102">ICorDebugNativeFrame2::IsChild (Método)</span><span class="sxs-lookup"><span data-stu-id="2373b-102">ICorDebugNativeFrame2::IsChild Method</span></span>

<span data-ttu-id="2373b-103">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="2373b-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2373b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2373b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2373b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2373b-105">Parameters</span></span>  

 `pIsChild`  
 <span data-ttu-id="2373b-106">enuncia Valor booleano que especifica si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="2373b-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2373b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2373b-107">Return Value</span></span>  

 <span data-ttu-id="2373b-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2373b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2373b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2373b-109">HRESULT</span></span>|<span data-ttu-id="2373b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2373b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2373b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2373b-111">S_OK</span></span>|<span data-ttu-id="2373b-112">El estado secundario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2373b-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="2373b-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2373b-113">E_FAIL</span></span>|<span data-ttu-id="2373b-114">No se pudo devolver el estado secundario.</span><span class="sxs-lookup"><span data-stu-id="2373b-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="2373b-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2373b-115">E_INVALIDARG</span></span>|<span data-ttu-id="2373b-116">`pIsChild` es null.</span><span class="sxs-lookup"><span data-stu-id="2373b-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2373b-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2373b-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2373b-118">Notas</span><span class="sxs-lookup"><span data-stu-id="2373b-118">Remarks</span></span>  

 <span data-ttu-id="2373b-119">El `IsChild` método devuelve `true` si el objeto de marco en el que se llama al método es un elemento secundario de otro marco.</span><span class="sxs-lookup"><span data-stu-id="2373b-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="2373b-120">Si este es el caso, use el método [ismatchingparentframe (](icordebugnativeframe2-ismatchingparentframe-method.md) para comprobar si un marco es su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="2373b-120">If this is the case, use the [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2373b-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2373b-121">Requirements</span></span>  

 <span data-ttu-id="2373b-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2373b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2373b-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2373b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2373b-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2373b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2373b-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2373b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2373b-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2373b-126">See also</span></span>

- [<span data-ttu-id="2373b-127">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2373b-127">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="2373b-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2373b-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2373b-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="2373b-129">Debugging</span></span>](index.md)
