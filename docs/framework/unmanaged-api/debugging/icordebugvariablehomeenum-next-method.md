---
title: 'ICorDebugVariableHomeEnum:: Next (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 9c2c16789fb61099c9b7c58154810739d225af1f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121921"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="2d336-102">ICorDebugVariableHomeEnum:: Next (método)</span><span class="sxs-lookup"><span data-stu-id="2d336-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="2d336-103">Obtiene el número especificado de instancias de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="2d336-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d336-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d336-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d336-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d336-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2d336-106">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="2d336-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="2d336-107">Una matriz de punteros, cada uno de los cuales apunta a un objeto [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) que proporciona información acerca de una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="2d336-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2d336-108">enuncia Número de instancias devueltas realmente en objetos.</span><span class="sxs-lookup"><span data-stu-id="2d336-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d336-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d336-109">Return Value</span></span>  
 <span data-ttu-id="2d336-110">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="2d336-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="2d336-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d336-111">HRESULT</span></span>|<span data-ttu-id="2d336-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d336-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2d336-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d336-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2d336-114">El número real de instancias recuperadas, como se refleja en `pceltFetched`, es menor que el número de instancias solicitadas.</span><span class="sxs-lookup"><span data-stu-id="2d336-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d336-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d336-115">Remarks</span></span>  
 <span data-ttu-id="2d336-116">El método [ICorDebugVariableHomeEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) recupera un máximo de `celt` objetos que comienzan en la posición actual del enumerador.</span><span class="sxs-lookup"><span data-stu-id="2d336-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="2d336-117">Cuando el método devuelve un valor, `pceltFetched` contiene el número real de objetos recuperados.</span><span class="sxs-lookup"><span data-stu-id="2d336-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d336-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d336-118">Requirements</span></span>  
 <span data-ttu-id="2d336-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d336-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d336-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d336-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d336-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d336-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d336-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d336-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d336-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d336-123">See also</span></span>

- [<span data-ttu-id="2d336-124">ICorDebugVariableHomeEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d336-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="2d336-125">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d336-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
