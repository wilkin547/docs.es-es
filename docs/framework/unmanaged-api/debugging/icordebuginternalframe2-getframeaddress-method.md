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
ms.openlocfilehash: 05a9ab58acb3bf5829fd231ae6d8bcc96ae06da6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724876"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="2b483-102">ICorDebugInternalFrame2::GetFrameAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="2b483-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>

<span data-ttu-id="2b483-103">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="2b483-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b483-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b483-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b483-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b483-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="2b483-106">enuncia Puntero a `CORDB_ADDRESS` para el marco interno.</span><span class="sxs-lookup"><span data-stu-id="2b483-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b483-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2b483-107">Return Value</span></span>  

 <span data-ttu-id="2b483-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2b483-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2b483-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b483-109">HRESULT</span></span>|<span data-ttu-id="2b483-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b483-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b483-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b483-111">S_OK</span></span>|<span data-ttu-id="2b483-112">La dirección del marco interno se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2b483-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="2b483-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b483-113">E_FAIL</span></span>|<span data-ttu-id="2b483-114">No se pudo devolver la dirección del marco interno.</span><span class="sxs-lookup"><span data-stu-id="2b483-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="2b483-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2b483-115">E_INVALIDARG</span></span>|<span data-ttu-id="2b483-116">`pAddress` es `null`.</span><span class="sxs-lookup"><span data-stu-id="2b483-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b483-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b483-117">Remarks</span></span>  

 <span data-ttu-id="2b483-118">El valor devuelto en `pAddress` se puede utilizar para determinar la ubicación del marco interno con respecto a otros marcos de la pila.</span><span class="sxs-lookup"><span data-stu-id="2b483-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="2b483-119">Incluso en equipos basados en IA-64, el marco interno solo vive en la pila y no hay ningún puntero correspondiente a la memoria auxiliar.</span><span class="sxs-lookup"><span data-stu-id="2b483-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b483-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b483-120">Requirements</span></span>  

 <span data-ttu-id="2b483-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b483-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b483-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b483-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b483-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b483-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b483-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b483-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b483-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b483-125">See also</span></span>

- [<span data-ttu-id="2b483-126">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b483-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="2b483-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2b483-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2b483-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="2b483-128">Debugging</span></span>](index.md)
