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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c30115a23f7f73662c9b3f4f4a09d45478ad687
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187296"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="5c4db-102">ICorDebugInternalFrame2::GetFrameAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="5c4db-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="5c4db-103">Devuelve la dirección de pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="5c4db-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c4db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c4db-104">Syntax</span></span>  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c4db-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c4db-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="5c4db-106">[out] Puntero a la `CORDB_ADDRESS` para el marco interno.</span><span class="sxs-lookup"><span data-stu-id="5c4db-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c4db-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5c4db-107">Return Value</span></span>  
 <span data-ttu-id="5c4db-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="5c4db-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5c4db-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c4db-109">HRESULT</span></span>|<span data-ttu-id="5c4db-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c4db-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c4db-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c4db-111">S_OK</span></span>|<span data-ttu-id="5c4db-112">La dirección del marco interno se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5c4db-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="5c4db-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c4db-113">E_FAIL</span></span>|<span data-ttu-id="5c4db-114">No se pudo devolver la dirección del marco interno.</span><span class="sxs-lookup"><span data-stu-id="5c4db-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="5c4db-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5c4db-115">E_INVALIDARG</span></span>|`pAddress` <span data-ttu-id="5c4db-116">es `null`.</span><span class="sxs-lookup"><span data-stu-id="5c4db-116">is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c4db-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c4db-117">Remarks</span></span>  
 <span data-ttu-id="5c4db-118">El valor devuelto en `pAddress` puede usarse para determinar la ubicación del marco interno en relación con otros marcos de la pila.</span><span class="sxs-lookup"><span data-stu-id="5c4db-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="5c4db-119">Incluso en equipos basados en IA-64, el marco interno se encuentra en la pila solo y no hay ningún puntero correspondiente a un almacén de respaldo.</span><span class="sxs-lookup"><span data-stu-id="5c4db-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c4db-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c4db-120">Requirements</span></span>  
 <span data-ttu-id="5c4db-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c4db-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c4db-122">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c4db-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c4db-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c4db-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5c4db-124">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5c4db-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c4db-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c4db-125">See also</span></span>

- [<span data-ttu-id="5c4db-126">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c4db-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="5c4db-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5c4db-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5c4db-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="5c4db-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
