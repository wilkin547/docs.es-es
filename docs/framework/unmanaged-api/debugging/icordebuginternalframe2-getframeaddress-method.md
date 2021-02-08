---
description: 'Más información sobre: ICorDebugInternalFrame2:: Getframeaddress ((método)'
title: ICorDebugInternalFrame2::GetFrameAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: bb745424680c5b9a5277badfbe2d96db46e2e3d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791119"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="ce88d-103">ICorDebugInternalFrame2::GetFrameAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="ce88d-103">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>

<span data-ttu-id="ce88d-104">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="ce88d-104">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce88d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce88d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce88d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce88d-106">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="ce88d-107">enuncia Puntero a `CORDB_ADDRESS` para el marco interno.</span><span class="sxs-lookup"><span data-stu-id="ce88d-107">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce88d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ce88d-108">Return Value</span></span>  

 <span data-ttu-id="ce88d-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ce88d-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ce88d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce88d-110">HRESULT</span></span>|<span data-ttu-id="ce88d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce88d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce88d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce88d-112">S_OK</span></span>|<span data-ttu-id="ce88d-113">La dirección del marco interno se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ce88d-113">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="ce88d-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce88d-114">E_FAIL</span></span>|<span data-ttu-id="ce88d-115">No se pudo devolver la dirección del marco interno.</span><span class="sxs-lookup"><span data-stu-id="ce88d-115">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="ce88d-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ce88d-116">E_INVALIDARG</span></span>|<span data-ttu-id="ce88d-117">`pAddress` es `null`.</span><span class="sxs-lookup"><span data-stu-id="ce88d-117">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce88d-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ce88d-118">Remarks</span></span>  

 <span data-ttu-id="ce88d-119">El valor devuelto en `pAddress` se puede utilizar para determinar la ubicación del marco interno con respecto a otros marcos de la pila.</span><span class="sxs-lookup"><span data-stu-id="ce88d-119">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="ce88d-120">Incluso en equipos basados en IA-64, el marco interno solo vive en la pila y no hay ningún puntero correspondiente a la memoria auxiliar.</span><span class="sxs-lookup"><span data-stu-id="ce88d-120">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce88d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce88d-121">Requirements</span></span>  

 <span data-ttu-id="ce88d-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce88d-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce88d-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce88d-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce88d-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce88d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce88d-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce88d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce88d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce88d-126">See also</span></span>

- [<span data-ttu-id="ce88d-127">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce88d-127">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="ce88d-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ce88d-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ce88d-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="ce88d-129">Debugging</span></span>](index.md)
