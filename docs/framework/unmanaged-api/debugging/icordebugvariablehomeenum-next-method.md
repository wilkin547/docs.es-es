---
title: Método ICorDebugVariableHomeEnum::Next
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be1ba87ae979911dd21647569725eafa2c80ffa6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080733"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="11d7a-102">Método ICorDebugVariableHomeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="11d7a-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="11d7a-103">Obtiene el número especificado de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancias que contienen información sobre las variables locales y los argumentos en una función.</span><span class="sxs-lookup"><span data-stu-id="11d7a-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d7a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11d7a-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11d7a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11d7a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="11d7a-106">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="11d7a-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="11d7a-107">Una matriz de punteros, cada uno de los cuales señala a un [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objeto que proporciona información sobre una variable local o argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="11d7a-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="11d7a-108">[out] El número de instancias realmente devueltos en los objetos.</span><span class="sxs-lookup"><span data-stu-id="11d7a-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11d7a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11d7a-109">Return Value</span></span>  
 <span data-ttu-id="11d7a-110">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="11d7a-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="11d7a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11d7a-111">HRESULT</span></span>|<span data-ttu-id="11d7a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="11d7a-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="11d7a-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="11d7a-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="11d7a-114">Recupera el número real de las instancias, tal como se refleja en `pceltFetched`, es menor que el número de instancias solicitadas.</span><span class="sxs-lookup"><span data-stu-id="11d7a-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11d7a-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11d7a-115">Remarks</span></span>  
 <span data-ttu-id="11d7a-116">El [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) método recupera un máximo de `celt` objetos que comienza en la posición actual del enumerador.</span><span class="sxs-lookup"><span data-stu-id="11d7a-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="11d7a-117">Cuando el método vuelve, `pceltFetched` contiene el número real de los objetos recuperados.</span><span class="sxs-lookup"><span data-stu-id="11d7a-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11d7a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11d7a-118">Requirements</span></span>  
 <span data-ttu-id="11d7a-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11d7a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11d7a-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11d7a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11d7a-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11d7a-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="11d7a-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="11d7a-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11d7a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="11d7a-123">See also</span></span>

- [<span data-ttu-id="11d7a-124">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="11d7a-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="11d7a-125">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="11d7a-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
