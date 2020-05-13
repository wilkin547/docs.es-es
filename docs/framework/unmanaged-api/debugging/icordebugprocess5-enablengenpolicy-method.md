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
ms.openlocfilehash: fa3cbfee0359b8477f9efe88fe72837b86611bf7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212807"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="dcf69-102">ICorDebugProcess5::EnableNGENPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="dcf69-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="dcf69-103">Establece un valor que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="dcf69-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dcf69-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcf69-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dcf69-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="dcf69-106">de Una constante [cordebugngenpolicy (](cordebugngenpolicy-enumeration.md) que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="dcf69-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcf69-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dcf69-107">Remarks</span></span>  
 <span data-ttu-id="dcf69-108">Si la Directiva se establece correctamente, el método devuelve `S_OK` .</span><span class="sxs-lookup"><span data-stu-id="dcf69-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="dcf69-109">Si `ePolicy` está fuera del intervalo de los valores enumerados definidos por [cordebugngenpolicy (](cordebugngenpolicy-enumeration.md), el método devuelve `E_INVALIDARG` y la llamada al método no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="dcf69-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="dcf69-110">Si la Directiva del generador de imágenes nativas (Ngen. exe) no se puede actualizar, el método devuelve `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="dcf69-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="dcf69-111">`ICorDebugProcess5::EnableNGenPolicy`Se puede llamar al método en cualquier momento durante la vigencia del proceso.</span><span class="sxs-lookup"><span data-stu-id="dcf69-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="dcf69-112">La Directiva está en vigor para todos los módulos que se cargan una vez establecida la Directiva.</span><span class="sxs-lookup"><span data-stu-id="dcf69-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf69-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcf69-113">Requirements</span></span>  
 <span data-ttu-id="dcf69-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcf69-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcf69-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcf69-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcf69-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcf69-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcf69-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcf69-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf69-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dcf69-118">See also</span></span>

- [<span data-ttu-id="dcf69-119">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dcf69-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="dcf69-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="dcf69-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="dcf69-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="dcf69-121">Debugging</span></span>](index.md)
