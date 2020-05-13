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
ms.openlocfilehash: 759ba7bd46f8231143e743aa5ffcabffeb99c3b6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205111"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="13c67-102">ICorDebugNativeFrame2::IsChild (Método)</span><span class="sxs-lookup"><span data-stu-id="13c67-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="13c67-103">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="13c67-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13c67-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13c67-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13c67-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="13c67-106">enuncia Valor booleano que especifica si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="13c67-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13c67-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="13c67-107">Return Value</span></span>  
 <span data-ttu-id="13c67-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="13c67-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="13c67-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13c67-109">HRESULT</span></span>|<span data-ttu-id="13c67-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="13c67-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13c67-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="13c67-111">S_OK</span></span>|<span data-ttu-id="13c67-112">El estado secundario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="13c67-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="13c67-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="13c67-113">E_FAIL</span></span>|<span data-ttu-id="13c67-114">No se pudo devolver el estado secundario.</span><span class="sxs-lookup"><span data-stu-id="13c67-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="13c67-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="13c67-115">E_INVALIDARG</span></span>|<span data-ttu-id="13c67-116">`pIsChild` es null.</span><span class="sxs-lookup"><span data-stu-id="13c67-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="13c67-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="13c67-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13c67-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="13c67-118">Remarks</span></span>  
 <span data-ttu-id="13c67-119">El `IsChild` método devuelve `true` si el objeto de marco en el que se llama al método es un elemento secundario de otro marco.</span><span class="sxs-lookup"><span data-stu-id="13c67-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="13c67-120">Si este es el caso, use el método [ismatchingparentframe (](icordebugnativeframe2-ismatchingparentframe-method.md) para comprobar si un marco es su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="13c67-120">If this is the case, use the [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13c67-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13c67-121">Requirements</span></span>  
 <span data-ttu-id="13c67-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13c67-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13c67-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13c67-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13c67-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13c67-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13c67-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13c67-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c67-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13c67-126">See also</span></span>

- [<span data-ttu-id="13c67-127">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="13c67-127">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="13c67-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="13c67-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="13c67-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="13c67-129">Debugging</span></span>](index.md)
