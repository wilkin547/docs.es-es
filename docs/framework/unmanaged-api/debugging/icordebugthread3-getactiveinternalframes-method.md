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
ms.openlocfilehash: 680af5afa3ebef5bcaf9e34580e421dcc8093aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178467"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="ca665-102">ICorDebugThread3::GetActiveInternalFrames (Método)</span><span class="sxs-lookup"><span data-stu-id="ca665-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="ca665-103">Devuelve una matriz de marcos internos[(ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objetos) en la pila.</span><span class="sxs-lookup"><span data-stu-id="ca665-103">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca665-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca665-104">Syntax</span></span>  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca665-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca665-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="ca665-106">[en] El número de fotogramas internos esperados en `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="ca665-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="ca665-107">[fuera] Puntero a `ULONG32` un que contiene el número de fotogramas internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="ca665-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="ca665-108">[adentro, fuera] Puntero a la dirección de una matriz de fotogramas internos en la pila.</span><span class="sxs-lookup"><span data-stu-id="ca665-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca665-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ca665-109">Return Value</span></span>  
 <span data-ttu-id="ca665-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ca665-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ca665-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca665-111">HRESULT</span></span>|<span data-ttu-id="ca665-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca665-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca665-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca665-113">S_OK</span></span>|<span data-ttu-id="ca665-114">El [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objeto se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca665-114">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="ca665-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ca665-115">E_INVALIDARG</span></span>|<span data-ttu-id="ca665-116">`cInternalFrames`no es `ppInternalFrames` cero `null`y `pcInternalFrames` `null`es, o es .</span><span class="sxs-lookup"><span data-stu-id="ca665-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="ca665-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="ca665-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="ca665-118">`ppInternalFrames`es menor que el recuento de fotogramas internos.</span><span class="sxs-lookup"><span data-stu-id="ca665-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ca665-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="ca665-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca665-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ca665-120">Remarks</span></span>  
 <span data-ttu-id="ca665-121">Los marcos internos son estructuras de datos insertadas en la pila por el tiempo de ejecución para almacenar datos temporales.</span><span class="sxs-lookup"><span data-stu-id="ca665-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="ca665-122">La primera `GetActiveInternalFrames`llamada, debe `cInternalFrames` establecer el parámetro en `ppInternalFrames` 0 (cero) y el parámetro en null.</span><span class="sxs-lookup"><span data-stu-id="ca665-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="ca665-123">Cuando `GetActiveInternalFrames` se `pcInternalFrames` devuelve por primera vez, contiene el recuento de los fotogramas internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="ca665-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="ca665-124">`GetActiveInternalFrames`entonces debe ser llamado una segunda vez.</span><span class="sxs-lookup"><span data-stu-id="ca665-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="ca665-125">Debe pasar el recuento`pcInternalFrames`adecuado `cInternalFrames` ( ) en el parámetro y especificar `ppInternalFrames`un puntero a una matriz de tamaño adecuado en .</span><span class="sxs-lookup"><span data-stu-id="ca665-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="ca665-126">Utilice el [método ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) para devolver marcos de pila reales.</span><span class="sxs-lookup"><span data-stu-id="ca665-126">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca665-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca665-127">Requirements</span></span>  
 <span data-ttu-id="ca665-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca665-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca665-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca665-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca665-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca665-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca665-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca665-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca665-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca665-132">See also</span></span>

- [<span data-ttu-id="ca665-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ca665-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ca665-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="ca665-134">Debugging</span></span>](index.md)
