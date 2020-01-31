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
ms.openlocfilehash: 2bb6fee00bb99555bc19f35e1250880cc3985f7f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790938"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="c7c3e-102">ICorDebugVariableHomeEnum:: Next (método)</span><span class="sxs-lookup"><span data-stu-id="c7c3e-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="c7c3e-103">Obtiene el número especificado de instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="c7c3e-103">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7c3e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7c3e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7c3e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c7c3e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c7c3e-106">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="c7c3e-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="c7c3e-107">Una matriz de punteros, cada uno de los cuales apunta a un objeto [ICorDebugVariableHome](icordebugvariablehome-interface.md) que proporciona información acerca de una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="c7c3e-107">An array of pointers, each of which points to a [ICorDebugVariableHome](icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c7c3e-108">enuncia Número de instancias devueltas realmente en objetos.</span><span class="sxs-lookup"><span data-stu-id="c7c3e-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7c3e-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c7c3e-109">Return Value</span></span>  
 <span data-ttu-id="c7c3e-110">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="c7c3e-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="c7c3e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7c3e-111">HRESULT</span></span>|<span data-ttu-id="c7c3e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7c3e-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c7c3e-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c7c3e-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c7c3e-114">El número real de instancias recuperadas, como se refleja en `pceltFetched`, es menor que el número de instancias solicitadas.</span><span class="sxs-lookup"><span data-stu-id="c7c3e-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7c3e-115">Notas</span><span class="sxs-lookup"><span data-stu-id="c7c3e-115">Remarks</span></span>  
 <span data-ttu-id="c7c3e-116">El método [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) recupera un máximo de `celt` objetos que comienzan en la posición actual del enumerador.</span><span class="sxs-lookup"><span data-stu-id="c7c3e-116">The [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="c7c3e-117">Cuando el método devuelve un valor, `pceltFetched` contiene el número real de objetos recuperados.</span><span class="sxs-lookup"><span data-stu-id="c7c3e-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7c3e-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c7c3e-118">Requirements</span></span>  
 <span data-ttu-id="c7c3e-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7c3e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7c3e-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7c3e-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7c3e-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7c3e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7c3e-122">**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7c3e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c3e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7c3e-123">See also</span></span>

- [<span data-ttu-id="c7c3e-124">ICorDebugVariableHomeEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7c3e-124">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="c7c3e-125">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7c3e-125">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
