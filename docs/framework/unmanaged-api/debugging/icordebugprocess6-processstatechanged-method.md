---
title: Método ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 6be216741e902b15efc3a3ece95cb4a4229960e3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212859"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="1385b-102">Método ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="1385b-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="1385b-103">Notifica a [ICorDebug](icordebug-interface.md) que el proceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="1385b-103">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1385b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1385b-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1385b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1385b-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="1385b-106">de Un miembro de la enumeración [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="1385b-106">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1385b-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1385b-107">Remarks</span></span>  
 <span data-ttu-id="1385b-108">El depurador llama a este método para notificar a [ICorDebug](icordebug-interface.md) que el proceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="1385b-108">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1385b-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1385b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1385b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1385b-110">Requirements</span></span>  
 <span data-ttu-id="1385b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1385b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1385b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1385b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1385b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1385b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1385b-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1385b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1385b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1385b-115">See also</span></span>

- [<span data-ttu-id="1385b-116">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="1385b-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="1385b-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1385b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
