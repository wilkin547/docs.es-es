---
description: 'Más información sobre: ICorDebugDebugEvent:: GetThread ((método)'
title: Método ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 1d476603572f31882f481d414e483c6712f1b5fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710418"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="8248f-103">Método ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="8248f-103">ICorDebugDebugEvent::GetThread Method</span></span>

<span data-ttu-id="8248f-104">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="8248f-104">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8248f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8248f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8248f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8248f-106">Parameters</span></span>  

 <span data-ttu-id="8248f-107">ppThread</span><span class="sxs-lookup"><span data-stu-id="8248f-107">ppThread</span></span>  
 <span data-ttu-id="8248f-108">[out] Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="8248f-108">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8248f-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8248f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8248f-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8248f-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8248f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8248f-111">Requirements</span></span>  

 <span data-ttu-id="8248f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8248f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8248f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8248f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8248f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8248f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8248f-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8248f-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8248f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8248f-116">See also</span></span>

- [<span data-ttu-id="8248f-117">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="8248f-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="8248f-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8248f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
