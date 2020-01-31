---
title: ICorDebugValue2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: c6f20b0f7927d79ee56b5b6962137d668dc048d1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791118"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="0c41b-102">ICorDebugValue2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c41b-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="0c41b-103">Extiende la interfaz "ICorDebugValue" para proporcionar compatibilidad con objetos "ICorDebugType".</span><span class="sxs-lookup"><span data-stu-id="0c41b-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c41b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0c41b-104">Methods</span></span>  
  
|<span data-ttu-id="0c41b-105">Método</span><span class="sxs-lookup"><span data-stu-id="0c41b-105">Method</span></span>|<span data-ttu-id="0c41b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c41b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c41b-107">GetExactType (método)</span><span class="sxs-lookup"><span data-stu-id="0c41b-107">GetExactType Method</span></span>](icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="0c41b-108">Obtiene un puntero de interfaz a un objeto `ICorDebugType` que representa el <xref:System.Type> de este valor.</span><span class="sxs-lookup"><span data-stu-id="0c41b-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c41b-109">Notas</span><span class="sxs-lookup"><span data-stu-id="0c41b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c41b-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="0c41b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c41b-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0c41b-111">Requirements</span></span>  
 <span data-ttu-id="0c41b-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c41b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c41b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c41b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c41b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c41b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c41b-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c41b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c41b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c41b-116">See also</span></span>

- [<span data-ttu-id="0c41b-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0c41b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

- [<span data-ttu-id="0c41b-118">ICorDebugValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c41b-118">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
