---
description: 'Más información acerca de: método icordebugprocess6::P rocessStateChanged (método)'
title: Método ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 8060c29598adf5d4bbe7bffb4cd6611ee19a2669
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691372"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="4c1e8-103">Método ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="4c1e8-103">ICorDebugProcess6::ProcessStateChanged Method</span></span>

<span data-ttu-id="4c1e8-104">Notifica a [ICorDebug](icordebug-interface.md) que el proceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4c1e8-104">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c1e8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c1e8-105">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c1e8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4c1e8-106">Parameters</span></span>  

 `change`  
 <span data-ttu-id="4c1e8-107">de Un miembro de la enumeración [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="4c1e8-107">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c1e8-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4c1e8-108">Remarks</span></span>  

 <span data-ttu-id="4c1e8-109">El depurador llama a este método para notificar a [ICorDebug](icordebug-interface.md) que el proceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4c1e8-109">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c1e8-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4c1e8-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c1e8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c1e8-111">Requirements</span></span>  

 <span data-ttu-id="4c1e8-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c1e8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c1e8-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c1e8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c1e8-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c1e8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c1e8-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c1e8-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c1e8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c1e8-116">See also</span></span>

- [<span data-ttu-id="4c1e8-117">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="4c1e8-117">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="4c1e8-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4c1e8-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
