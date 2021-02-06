---
description: 'Más información sobre: ICorDebugProcess5:: Enablengenpolicy ((método)'
title: ICorDebugProcess5::EnableNGENPolicy (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
ms.openlocfilehash: 0f3194893665bfe9fff802a293aaafed8254f2e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649928"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="73f07-103">ICorDebugProcess5::EnableNGENPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="73f07-103">ICorDebugProcess5::EnableNGENPolicy Method</span></span>

<span data-ttu-id="73f07-104">Establece un valor que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="73f07-104">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f07-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73f07-105">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73f07-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73f07-106">Parameters</span></span>  

 `ePolicy`  
 <span data-ttu-id="73f07-107">de Una constante [cordebugngenpolicy (](cordebugngenpolicy-enumeration.md) que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="73f07-107">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73f07-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73f07-108">Remarks</span></span>  

 <span data-ttu-id="73f07-109">Si la Directiva se establece correctamente, el método devuelve `S_OK` .</span><span class="sxs-lookup"><span data-stu-id="73f07-109">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="73f07-110">Si `ePolicy` está fuera del intervalo de los valores enumerados definidos por [cordebugngenpolicy (](cordebugngenpolicy-enumeration.md), el método devuelve `E_INVALIDARG` y la llamada al método no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="73f07-110">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="73f07-111">Si no se puede actualizar la Directiva del generador de imágenes nativas (Ngen.exe), el método devuelve `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="73f07-111">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="73f07-112">`ICorDebugProcess5::EnableNGenPolicy`Se puede llamar al método en cualquier momento durante la vigencia del proceso.</span><span class="sxs-lookup"><span data-stu-id="73f07-112">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="73f07-113">La Directiva está en vigor para todos los módulos que se cargan una vez establecida la Directiva.</span><span class="sxs-lookup"><span data-stu-id="73f07-113">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73f07-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73f07-114">Requirements</span></span>  

 <span data-ttu-id="73f07-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73f07-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73f07-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73f07-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73f07-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73f07-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73f07-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73f07-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f07-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="73f07-119">See also</span></span>

- [<span data-ttu-id="73f07-120">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73f07-120">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="73f07-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="73f07-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="73f07-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="73f07-122">Debugging</span></span>](index.md)
