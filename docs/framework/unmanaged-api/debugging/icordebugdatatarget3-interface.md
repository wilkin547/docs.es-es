---
title: Interfaz de ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 57ef9b567d57c77c523ca6daefcf80b1d7de66d1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976413"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="bf9cd-102">Interfaz de ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="bf9cd-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="bf9cd-103">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="bf9cd-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="bf9cd-104">Método</span><span class="sxs-lookup"><span data-stu-id="bf9cd-104">Method</span></span>  
  
|<span data-ttu-id="bf9cd-105">Método</span><span class="sxs-lookup"><span data-stu-id="bf9cd-105">Method</span></span>|<span data-ttu-id="bf9cd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf9cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf9cd-107">Método GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="bf9cd-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="bf9cd-108">Obtiene una lista de los módulos que se han cargado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="bf9cd-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf9cd-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bf9cd-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf9cd-110">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bf9cd-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="bf9cd-111">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="bf9cd-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf9cd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf9cd-112">Requirements</span></span>  
 <span data-ttu-id="bf9cd-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf9cd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf9cd-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf9cd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf9cd-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf9cd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf9cd-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf9cd-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9cd-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf9cd-117">See also</span></span>

- [<span data-ttu-id="bf9cd-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="bf9cd-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="bf9cd-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="bf9cd-119">Debugging</span></span>](index.md)
