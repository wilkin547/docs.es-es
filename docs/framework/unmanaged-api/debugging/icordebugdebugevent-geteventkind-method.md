---
description: 'Más información sobre: ICorDebugDebugEvent:: GetEventKind (método)'
title: Método ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 9e15eb82195fae8aa3797ea47cb04d0bb407d2ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764325"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="5707f-103">Método ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="5707f-103">ICorDebugDebugEvent::GetEventKind Method</span></span>

<span data-ttu-id="5707f-104">Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.</span><span class="sxs-lookup"><span data-stu-id="5707f-104">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5707f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5707f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5707f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5707f-106">Parameters</span></span>  

 <span data-ttu-id="5707f-107">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="5707f-107">pDebugEventKind</span></span>  
 <span data-ttu-id="5707f-108">Un puntero a un miembro de la enumeración [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) que indica el tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="5707f-108">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5707f-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5707f-109">Remarks</span></span>  

 <span data-ttu-id="5707f-110">Según el valor de `pDebugEventKind`, se puede llamar a `QueryInterface` para obtener una interfaz de evento de depuración más precisa con datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="5707f-110">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5707f-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5707f-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5707f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5707f-112">Requirements</span></span>  

 <span data-ttu-id="5707f-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5707f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5707f-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5707f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5707f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5707f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5707f-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5707f-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5707f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5707f-117">See also</span></span>

- [<span data-ttu-id="5707f-118">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="5707f-118">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="5707f-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5707f-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
