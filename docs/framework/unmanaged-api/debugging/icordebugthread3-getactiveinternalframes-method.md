---
description: 'Más información sobre: ICorDebugThread3:: GetActiveInternalFrames ((método)'
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
ms.openlocfilehash: f228dd84708478bb364ac09407a68df3e8d971b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800986"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="fb9e4-103">ICorDebugThread3::GetActiveInternalFrames (Método)</span><span class="sxs-lookup"><span data-stu-id="fb9e4-103">ICorDebugThread3::GetActiveInternalFrames Method</span></span>

<span data-ttu-id="fb9e4-104">Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) en la pila.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-104">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb9e4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb9e4-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb9e4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb9e4-106">Parameters</span></span>  

 `cInternalFrames`  
 <span data-ttu-id="fb9e4-107">de Número de fotogramas internos esperados en `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="fb9e4-107">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="fb9e4-108">enuncia Un puntero a un `ULONG32` valor de que contiene el número de Marcos internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-108">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="fb9e4-109">[in, out] Puntero a la dirección de una matriz de Marcos internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-109">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb9e4-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fb9e4-110">Return Value</span></span>  

 <span data-ttu-id="fb9e4-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fb9e4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb9e4-112">HRESULT</span></span>|<span data-ttu-id="fb9e4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb9e4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb9e4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb9e4-114">S_OK</span></span>|<span data-ttu-id="fb9e4-115">El objeto [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-115">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="fb9e4-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fb9e4-116">E_INVALIDARG</span></span>|<span data-ttu-id="fb9e4-117">`cInternalFrames` no es cero y `ppInternalFrames` es `null` , o `pcInternalFrames` es `null` .</span><span class="sxs-lookup"><span data-stu-id="fb9e4-117">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="fb9e4-118">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="fb9e4-118">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="fb9e4-119">`ppInternalFrames` es menor que el número de Marcos internos.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-119">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="fb9e4-120">Excepciones</span><span class="sxs-lookup"><span data-stu-id="fb9e4-120">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb9e4-121">Notas</span><span class="sxs-lookup"><span data-stu-id="fb9e4-121">Remarks</span></span>  

 <span data-ttu-id="fb9e4-122">Los marcos internos son estructuras de datos insertadas en la pila por el motor en tiempo de ejecución para almacenar datos temporales.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-122">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="fb9e4-123">Cuando se llama por primera vez `GetActiveInternalFrames` , se debe establecer el `cInternalFrames` parámetro en 0 (cero) y el `ppInternalFrames` parámetro en NULL.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-123">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="fb9e4-124">Cuando se `GetActiveInternalFrames` devuelve por primera vez, `pcInternalFrames` contiene el recuento de los marcos internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-124">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="fb9e4-125">`GetActiveInternalFrames` a continuación, debe llamarse una segunda vez.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-125">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="fb9e4-126">Debe pasar el recuento adecuado ( `pcInternalFrames` ) en el `cInternalFrames` parámetro y especificar un puntero a una matriz de tamaño adecuado en `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="fb9e4-126">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="fb9e4-127">Use el método [ICorDebugStackWalk:: GetFrame](icordebugthread3-getactiveinternalframes-method.md) para devolver los marcos de pila reales.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-127">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb9e4-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb9e4-128">Requirements</span></span>  

 <span data-ttu-id="fb9e4-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb9e4-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb9e4-130">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb9e4-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb9e4-131">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb9e4-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb9e4-132">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb9e4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb9e4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb9e4-133">See also</span></span>

- [<span data-ttu-id="fb9e4-134">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fb9e4-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fb9e4-135">Depuración</span><span class="sxs-lookup"><span data-stu-id="fb9e4-135">Debugging</span></span>](index.md)
