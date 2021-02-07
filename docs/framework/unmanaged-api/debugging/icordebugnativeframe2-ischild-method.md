---
description: 'Más información sobre: ICorDebugNativeFrame2:: Ischild ((método)'
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
ms.openlocfilehash: 7c698c5a49ee445b4ba9c591c96f700f86a86c32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722300"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="65486-103">ICorDebugNativeFrame2::IsChild (Método)</span><span class="sxs-lookup"><span data-stu-id="65486-103">ICorDebugNativeFrame2::IsChild Method</span></span>

<span data-ttu-id="65486-104">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="65486-104">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65486-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65486-105">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65486-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65486-106">Parameters</span></span>  

 `pIsChild`  
 <span data-ttu-id="65486-107">enuncia Valor booleano que especifica si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="65486-107">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65486-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="65486-108">Return Value</span></span>  

 <span data-ttu-id="65486-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="65486-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="65486-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65486-110">HRESULT</span></span>|<span data-ttu-id="65486-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="65486-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65486-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="65486-112">S_OK</span></span>|<span data-ttu-id="65486-113">El estado secundario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="65486-113">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="65486-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65486-114">E_FAIL</span></span>|<span data-ttu-id="65486-115">No se pudo devolver el estado secundario.</span><span class="sxs-lookup"><span data-stu-id="65486-115">The child status could not be returned.</span></span>|  
|<span data-ttu-id="65486-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="65486-116">E_INVALIDARG</span></span>|<span data-ttu-id="65486-117">`pIsChild` es null.</span><span class="sxs-lookup"><span data-stu-id="65486-117">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="65486-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="65486-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65486-119">Notas</span><span class="sxs-lookup"><span data-stu-id="65486-119">Remarks</span></span>  

 <span data-ttu-id="65486-120">El `IsChild` método devuelve `true` si el objeto de marco en el que se llama al método es un elemento secundario de otro marco.</span><span class="sxs-lookup"><span data-stu-id="65486-120">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="65486-121">Si este es el caso, use el método [ismatchingparentframe (](icordebugnativeframe2-ismatchingparentframe-method.md) para comprobar si un marco es su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="65486-121">If this is the case, use the [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65486-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65486-122">Requirements</span></span>  

 <span data-ttu-id="65486-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65486-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65486-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65486-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65486-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65486-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65486-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65486-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65486-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="65486-127">See also</span></span>

- [<span data-ttu-id="65486-128">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65486-128">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="65486-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="65486-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="65486-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="65486-130">Debugging</span></span>](index.md)
