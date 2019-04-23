---
title: Método ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9bd4cd44eca9b12ab8773fd75b6262579cfe8e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206088"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="c427c-102">Método ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="c427c-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="c427c-103">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="c427c-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c427c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c427c-104">Syntax</span></span>  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c427c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c427c-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="c427c-106">Un puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado de contenedor o **null** si se produce un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="c427c-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c427c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c427c-107">Return Value</span></span>  
 <span data-ttu-id="c427c-108">`S_OK` Si la llamada al método se realiza correctamente; en caso contrario, `S_FALSE`, y `ppAssembly` es **null**.</span><span class="sxs-lookup"><span data-stu-id="c427c-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c427c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c427c-109">Remarks</span></span>  
 <span data-ttu-id="c427c-110">Si este ensamblado se ha combinado con otros dentro de un solo ensamblado de contenedor, este método devuelve el ensamblado de contenedor.</span><span class="sxs-lookup"><span data-stu-id="c427c-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="c427c-111">Para obtener más información y la terminología, consulte el [icordebugprocess6:: Enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) tema.</span><span class="sxs-lookup"><span data-stu-id="c427c-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c427c-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c427c-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c427c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c427c-113">Requirements</span></span>  
 <span data-ttu-id="c427c-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c427c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c427c-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c427c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c427c-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c427c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c427c-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c427c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c427c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c427c-118">See also</span></span>

- [<span data-ttu-id="c427c-119">ICorDebugAssembly3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c427c-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="c427c-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c427c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
