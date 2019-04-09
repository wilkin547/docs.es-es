---
title: ICorDebugThread3::GetActiveInternalFrames (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e264f2361c739536d15fbf31d366db74e107bac2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085108"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="fa15c-102">ICorDebugThread3::GetActiveInternalFrames (Método)</span><span class="sxs-lookup"><span data-stu-id="fa15c-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="fa15c-103">Devuelve una matriz de marcos internos ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objetos) en la pila.</span><span class="sxs-lookup"><span data-stu-id="fa15c-103">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa15c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa15c-104">Syntax</span></span>  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa15c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa15c-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="fa15c-106">[in] El número de marcos internos esperados en `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="fa15c-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="fa15c-107">[out] Un puntero a un `ULONG32` que contiene el número de marcos internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="fa15c-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="fa15c-108">[in, out] Un puntero a la dirección de una matriz de marcos internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="fa15c-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa15c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fa15c-109">Return Value</span></span>  
 <span data-ttu-id="fa15c-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="fa15c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fa15c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa15c-111">HRESULT</span></span>|<span data-ttu-id="fa15c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa15c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa15c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa15c-113">S_OK</span></span>|<span data-ttu-id="fa15c-114">El [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objeto se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fa15c-114">The [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="fa15c-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fa15c-115">E_INVALIDARG</span></span>|`cInternalFrames` <span data-ttu-id="fa15c-116">no es cero y `ppInternalFrames` es `null`, o `pcInternalFrames` es `null`.</span><span class="sxs-lookup"><span data-stu-id="fa15c-116">is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="fa15c-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="fa15c-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|`ppInternalFrames` <span data-ttu-id="fa15c-118">es menor que el recuento de tramas internos.</span><span class="sxs-lookup"><span data-stu-id="fa15c-118">is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="fa15c-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="fa15c-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa15c-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa15c-120">Remarks</span></span>  
 <span data-ttu-id="fa15c-121">Los marcos internos son estructuras de datos que se insertan en la pila, el tiempo de ejecución para almacenar datos temporales.</span><span class="sxs-lookup"><span data-stu-id="fa15c-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="fa15c-122">Cuando llama `GetActiveInternalFrames`, debe establecer el `cInternalFrames` parámetro en 0 (cero) y el `ppInternalFrames` parámetro en null.</span><span class="sxs-lookup"><span data-stu-id="fa15c-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="fa15c-123">Cuando `GetActiveInternalFrames` devuelve en primer lugar, `pcInternalFrames` contiene el número de marcos internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="fa15c-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 `GetActiveInternalFrames` <span data-ttu-id="fa15c-124">a continuación, se debe llamar una segunda vez.</span><span class="sxs-lookup"><span data-stu-id="fa15c-124">should then be called a second time.</span></span> <span data-ttu-id="fa15c-125">Debe pasar el número apropiado (`pcInternalFrames`) en el `cInternalFrames` parámetro, y especifique un puntero a una matriz de tamaño adecuado en `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="fa15c-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="fa15c-126">Use la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) marcos de pila del método para devolver real.</span><span class="sxs-lookup"><span data-stu-id="fa15c-126">Use the [ICorDebugStackWalk::GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa15c-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa15c-127">Requirements</span></span>  
 <span data-ttu-id="fa15c-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa15c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa15c-129">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa15c-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa15c-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa15c-130">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fa15c-131">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fa15c-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa15c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa15c-132">See also</span></span>

- [<span data-ttu-id="fa15c-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fa15c-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fa15c-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="fa15c-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
