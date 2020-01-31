---
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
ms.openlocfilehash: 9497bea9b7cc5eb98876c923858dbcbc6adf9d07
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792447"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="4a503-102">ICorDebugProcess5::EnableNGENPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="4a503-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="4a503-103">Establece un valor que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="4a503-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a503-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a503-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a503-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4a503-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="4a503-106">de Una constante [cordebugngenpolicy (](cordebugngenpolicy-enumeration.md) que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="4a503-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a503-107">Notas</span><span class="sxs-lookup"><span data-stu-id="4a503-107">Remarks</span></span>  
 <span data-ttu-id="4a503-108">Si la Directiva se establece correctamente, el método devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="4a503-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="4a503-109">Si `ePolicy` está fuera del intervalo de valores enumerados definidos por [cordebugngenpolicy (](cordebugngenpolicy-enumeration.md), el método devuelve `E_INVALIDARG` y la llamada al método no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="4a503-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="4a503-110">Si la Directiva del generador de imágenes nativas (Ngen. exe) no se puede actualizar, el método devuelve `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="4a503-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="4a503-111">Se puede llamar al método `ICorDebugProcess5::EnableNGenPolicy` en cualquier momento durante la vigencia del proceso.</span><span class="sxs-lookup"><span data-stu-id="4a503-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="4a503-112">La Directiva está en vigor para todos los módulos que se cargan una vez establecida la Directiva.</span><span class="sxs-lookup"><span data-stu-id="4a503-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a503-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4a503-113">Requirements</span></span>  
 <span data-ttu-id="4a503-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a503-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a503-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a503-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a503-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a503-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a503-117">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a503-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a503-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a503-118">See also</span></span>

- [<span data-ttu-id="4a503-119">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a503-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="4a503-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4a503-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4a503-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="4a503-121">Debugging</span></span>](index.md)
