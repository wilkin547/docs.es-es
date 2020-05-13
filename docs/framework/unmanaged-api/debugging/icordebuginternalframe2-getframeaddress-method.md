---
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
ms.openlocfilehash: 51c8f9a2b66d7b2553949056f7cdbedcf5ea37d6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209921"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="33afb-102">ICorDebugInternalFrame2::GetFrameAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="33afb-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="33afb-103">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="33afb-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33afb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33afb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33afb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33afb-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="33afb-106">enuncia Puntero a `CORDB_ADDRESS` para el marco interno.</span><span class="sxs-lookup"><span data-stu-id="33afb-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33afb-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33afb-107">Return Value</span></span>  
 <span data-ttu-id="33afb-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="33afb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="33afb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="33afb-109">HRESULT</span></span>|<span data-ttu-id="33afb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="33afb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33afb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="33afb-111">S_OK</span></span>|<span data-ttu-id="33afb-112">La dirección del marco interno se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="33afb-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="33afb-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="33afb-113">E_FAIL</span></span>|<span data-ttu-id="33afb-114">No se pudo devolver la dirección del marco interno.</span><span class="sxs-lookup"><span data-stu-id="33afb-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="33afb-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="33afb-115">E_INVALIDARG</span></span>|<span data-ttu-id="33afb-116">`pAddress` es `null`.</span><span class="sxs-lookup"><span data-stu-id="33afb-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33afb-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33afb-117">Remarks</span></span>  
 <span data-ttu-id="33afb-118">El valor devuelto en `pAddress` se puede utilizar para determinar la ubicación del marco interno con respecto a otros marcos de la pila.</span><span class="sxs-lookup"><span data-stu-id="33afb-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="33afb-119">Incluso en equipos basados en IA-64, el marco interno solo vive en la pila y no hay ningún puntero correspondiente a la memoria auxiliar.</span><span class="sxs-lookup"><span data-stu-id="33afb-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33afb-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33afb-120">Requirements</span></span>  
 <span data-ttu-id="33afb-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33afb-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33afb-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33afb-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33afb-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33afb-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33afb-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33afb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33afb-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33afb-125">See also</span></span>

- [<span data-ttu-id="33afb-126">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33afb-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="33afb-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="33afb-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="33afb-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="33afb-128">Debugging</span></span>](index.md)
