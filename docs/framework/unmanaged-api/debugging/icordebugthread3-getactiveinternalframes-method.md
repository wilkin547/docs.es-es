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
ms.openlocfilehash: 25cd3e05bc80dd39d2ca558bb4dd5fb77d255f5a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791397"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="3a8b9-102">ICorDebugThread3::GetActiveInternalFrames (Método)</span><span class="sxs-lookup"><span data-stu-id="3a8b9-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="3a8b9-103">Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) en la pila.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-103">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a8b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a8b9-104">Syntax</span></span>  
  
```cpp 
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a8b9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3a8b9-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="3a8b9-106">de Número de fotogramas internos esperados en `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="3a8b9-107">enuncia Puntero a una `ULONG32` que contiene el número de Marcos internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="3a8b9-108">[in, out] Puntero a la dirección de una matriz de Marcos internos de la pila.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a8b9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3a8b9-109">Return Value</span></span>  
 <span data-ttu-id="3a8b9-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3a8b9-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a8b9-111">HRESULT</span></span>|<span data-ttu-id="3a8b9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a8b9-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a8b9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a8b9-113">S_OK</span></span>|<span data-ttu-id="3a8b9-114">El objeto [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-114">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="3a8b9-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3a8b9-115">E_INVALIDARG</span></span>|<span data-ttu-id="3a8b9-116">`cInternalFrames` no es cero y `ppInternalFrames` es `null`o `pcInternalFrames` es `null`.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="3a8b9-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="3a8b9-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="3a8b9-118">`ppInternalFrames` es menor que el número de Marcos internos.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="3a8b9-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="3a8b9-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a8b9-120">Notas</span><span class="sxs-lookup"><span data-stu-id="3a8b9-120">Remarks</span></span>  
 <span data-ttu-id="3a8b9-121">Los marcos internos son estructuras de datos insertadas en la pila por el motor en tiempo de ejecución para almacenar datos temporales.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="3a8b9-122">Cuando llame por primera vez a `GetActiveInternalFrames`, debe establecer el parámetro `cInternalFrames` en 0 (cero) y el parámetro `ppInternalFrames` en NULL.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="3a8b9-123">Cuando `GetActiveInternalFrames` devuelve primero, `pcInternalFrames` contiene el recuento de los marcos internos en la pila.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="3a8b9-124">a continuación, se debe llamar a `GetActiveInternalFrames` por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="3a8b9-125">Debe pasar el recuento adecuado (`pcInternalFrames`) en el parámetro `cInternalFrames` y especificar un puntero a una matriz de tamaño adecuado en `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="3a8b9-126">Use el método [ICorDebugStackWalk:: GetFrame](icordebugthread3-getactiveinternalframes-method.md) para devolver los marcos de pila reales.</span><span class="sxs-lookup"><span data-stu-id="3a8b9-126">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a8b9-127">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3a8b9-127">Requirements</span></span>  
 <span data-ttu-id="3a8b9-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a8b9-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a8b9-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a8b9-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a8b9-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a8b9-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a8b9-131">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a8b9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8b9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a8b9-132">See also</span></span>

- [<span data-ttu-id="3a8b9-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3a8b9-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3a8b9-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="3a8b9-134">Debugging</span></span>](index.md)
