---
description: 'Más información sobre: ICorDebugVariableHomeEnum:: Next (método)'
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
ms.openlocfilehash: 0aa0174e67bceaa724ddfeadc2560d12e112b859
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790612"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="5cece-103">ICorDebugVariableHomeEnum:: Next (método)</span><span class="sxs-lookup"><span data-stu-id="5cece-103">ICorDebugVariableHomeEnum::Next Method</span></span>

<span data-ttu-id="5cece-104">Obtiene el número especificado de instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="5cece-104">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cece-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5cece-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cece-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5cece-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="5cece-107">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="5cece-107">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="5cece-108">Una matriz de punteros, cada uno de los cuales apunta a un objeto [ICorDebugVariableHome](icordebugvariablehome-interface.md) que proporciona información acerca de una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="5cece-108">An array of pointers, each of which points to a [ICorDebugVariableHome](icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5cece-109">enuncia Número de instancias devueltas realmente en objetos.</span><span class="sxs-lookup"><span data-stu-id="5cece-109">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cece-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5cece-110">Return Value</span></span>  

 <span data-ttu-id="5cece-111">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="5cece-111">The method returns the following values.</span></span>  
  
|<span data-ttu-id="5cece-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5cece-112">HRESULT</span></span>|<span data-ttu-id="5cece-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cece-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5cece-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5cece-114">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5cece-115">El número real de instancias recuperadas, como se refleja en `pceltFetched` , es menor que el número de instancias solicitadas.</span><span class="sxs-lookup"><span data-stu-id="5cece-115">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cece-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5cece-116">Remarks</span></span>  

 <span data-ttu-id="5cece-117">El método [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) recupera un máximo de  `celt` objetos a partir de la posición actual del enumerador.</span><span class="sxs-lookup"><span data-stu-id="5cece-117">The [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="5cece-118">Cuando el método vuelve, `pceltFetched` contiene el número real de objetos recuperados.</span><span class="sxs-lookup"><span data-stu-id="5cece-118">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cece-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5cece-119">Requirements</span></span>  

 <span data-ttu-id="5cece-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cece-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cece-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cece-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cece-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cece-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cece-123">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cece-123">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cece-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cece-124">See also</span></span>

- [<span data-ttu-id="5cece-125">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="5cece-125">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="5cece-126">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="5cece-126">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
