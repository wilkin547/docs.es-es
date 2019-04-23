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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9503c12da9e98fbd43f3904aad25c5d10655cec2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075566"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="2e250-102">ICorDebugNativeFrame2::IsChild (Método)</span><span class="sxs-lookup"><span data-stu-id="2e250-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="2e250-103">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="2e250-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e250-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e250-104">Syntax</span></span>  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e250-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e250-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="2e250-106">[out] Un valor booleano que especifica si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="2e250-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e250-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2e250-107">Return Value</span></span>  
 <span data-ttu-id="2e250-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2e250-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2e250-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e250-109">HRESULT</span></span>|<span data-ttu-id="2e250-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e250-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e250-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e250-111">S_OK</span></span>|<span data-ttu-id="2e250-112">El estado del secundario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2e250-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="2e250-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e250-113">E_FAIL</span></span>|<span data-ttu-id="2e250-114">No se pudo devolver el estado del elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="2e250-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="2e250-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2e250-115">E_INVALIDARG</span></span>|<span data-ttu-id="2e250-116">`pIsChild` es null.</span><span class="sxs-lookup"><span data-stu-id="2e250-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2e250-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2e250-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e250-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e250-118">Remarks</span></span>  
 <span data-ttu-id="2e250-119">El `IsChild` devuelve del método `true` si el objeto de marco en el que se llama al método es un elemento secundario de otro marco.</span><span class="sxs-lookup"><span data-stu-id="2e250-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="2e250-120">Si este es el caso, utilice el [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) método para comprobar si un marco es su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="2e250-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e250-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e250-121">Requirements</span></span>  
 <span data-ttu-id="2e250-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e250-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e250-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e250-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e250-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e250-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e250-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e250-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e250-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e250-126">See also</span></span>

- [<span data-ttu-id="2e250-127">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e250-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="2e250-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2e250-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2e250-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="2e250-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
