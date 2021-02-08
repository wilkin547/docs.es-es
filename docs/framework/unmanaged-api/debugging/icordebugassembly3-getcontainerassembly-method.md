---
description: 'Más información sobre: método icordebugassembly3:: GetContainerAssembly (método)'
title: Método ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 5a6bc6dfb1c8403137a9444ff1cc4f64e75da65d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791522"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="8d0e0-103">Método ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="8d0e0-103">ICorDebugAssembly3::GetContainerAssembly Method</span></span>

<span data-ttu-id="8d0e0-104">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="8d0e0-104">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d0e0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d0e0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d0e0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d0e0-106">Parameters</span></span>  

 `ppAssembly`  
 <span data-ttu-id="8d0e0-107">Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado de contenedor, o **null** si se produce un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="8d0e0-107">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d0e0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8d0e0-108">Return Value</span></span>  

 <span data-ttu-id="8d0e0-109">`S_OK` Si la llamada al método se realiza correctamente; de lo contrario, `S_FALSE` y `ppAssembly` es **null**.</span><span class="sxs-lookup"><span data-stu-id="8d0e0-109">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d0e0-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8d0e0-110">Remarks</span></span>  

 <span data-ttu-id="8d0e0-111">Si este ensamblado se ha combinado con otros dentro de un solo ensamblado de contenedor, este método devuelve el ensamblado de contenedor.</span><span class="sxs-lookup"><span data-stu-id="8d0e0-111">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="8d0e0-112">Para obtener más información y terminología, vea el tema [método icordebugprocess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8d0e0-112">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d0e0-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8d0e0-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d0e0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d0e0-114">Requirements</span></span>  

 <span data-ttu-id="8d0e0-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d0e0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d0e0-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d0e0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d0e0-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d0e0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d0e0-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d0e0-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d0e0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d0e0-119">See also</span></span>

- [<span data-ttu-id="8d0e0-120">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="8d0e0-120">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="8d0e0-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8d0e0-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
