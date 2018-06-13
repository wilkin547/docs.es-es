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
ms.openlocfilehash: d088aaaaa80ee3513a37ea0345d720832504c005
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421153"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="19490-102">ICorDebugInternalFrame2::GetFrameAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="19490-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="19490-103">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="19490-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19490-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19490-104">Syntax</span></span>  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19490-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19490-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="19490-106">[out] Puntero a la `CORDB_ADDRESS` para el marco interno.</span><span class="sxs-lookup"><span data-stu-id="19490-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19490-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="19490-107">Return Value</span></span>  
 <span data-ttu-id="19490-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="19490-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="19490-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19490-109">HRESULT</span></span>|<span data-ttu-id="19490-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="19490-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19490-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="19490-111">S_OK</span></span>|<span data-ttu-id="19490-112">La dirección del marco interno se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="19490-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="19490-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19490-113">E_FAIL</span></span>|<span data-ttu-id="19490-114">No se pudo devolver la dirección del marco interno.</span><span class="sxs-lookup"><span data-stu-id="19490-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="19490-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="19490-115">E_INVALIDARG</span></span>|<span data-ttu-id="19490-116">El valor de `pAddress` es `null`.</span><span class="sxs-lookup"><span data-stu-id="19490-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19490-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19490-117">Remarks</span></span>  
 <span data-ttu-id="19490-118">El valor devuelto en `pAddress` puede utilizarse para determinar la ubicación del marco interno en relación con otros marcos de la pila.</span><span class="sxs-lookup"><span data-stu-id="19490-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="19490-119">Incluso en equipos basados en IA-64, el marco interno se mantiene en la pila solo y no hay ningún puntero correspondiente a un almacén de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="19490-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19490-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19490-120">Requirements</span></span>  
 <span data-ttu-id="19490-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19490-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19490-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19490-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19490-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19490-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19490-124">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19490-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19490-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="19490-125">See Also</span></span>  
 [<span data-ttu-id="19490-126">ICorDebugInternalFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="19490-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="19490-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="19490-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="19490-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="19490-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
