---
title: Interfaz ICorDebugBoxValue
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
ms.openlocfilehash: 1ec54f4fe36aaf38d7c0ce0586733729bd2fddea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784465"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="dcb34-102">Interfaz ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="dcb34-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="dcb34-103">Subclase de "ICorDebugHeapValue" que representa un objeto de clase de valor con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="dcb34-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dcb34-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="dcb34-104">Methods</span></span>  
  
|<span data-ttu-id="dcb34-105">Método</span><span class="sxs-lookup"><span data-stu-id="dcb34-105">Method</span></span>|<span data-ttu-id="dcb34-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcb34-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dcb34-107">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="dcb34-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="dcb34-108">Obtiene un puntero de interfaz a la instancia "ICorDebugObjectValue" con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="dcb34-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcb34-109">Notas</span><span class="sxs-lookup"><span data-stu-id="dcb34-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dcb34-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="dcb34-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcb34-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="dcb34-111">Requirements</span></span>  
 <span data-ttu-id="dcb34-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcb34-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcb34-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcb34-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcb34-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcb34-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcb34-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcb34-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb34-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcb34-116">See also</span></span>

- [<span data-ttu-id="dcb34-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="dcb34-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
