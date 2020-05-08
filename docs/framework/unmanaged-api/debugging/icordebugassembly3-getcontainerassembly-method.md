---
title: Método ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 068a08d70f2443edfe0970ec1ffb8cba9953c6b9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894846"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="52db0-102">Método ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="52db0-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="52db0-103">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="52db0-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52db0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52db0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52db0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52db0-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="52db0-106">Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado de contenedor, o **null** si se produce un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="52db0-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52db0-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52db0-107">Return Value</span></span>  
 <span data-ttu-id="52db0-108">`S_OK`Si la llamada al método se realiza correctamente; de lo `S_FALSE`contrario, `ppAssembly` y es **null**.</span><span class="sxs-lookup"><span data-stu-id="52db0-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52db0-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52db0-109">Remarks</span></span>  
 <span data-ttu-id="52db0-110">Si este ensamblado se ha combinado con otros dentro de un solo ensamblado de contenedor, este método devuelve el ensamblado de contenedor.</span><span class="sxs-lookup"><span data-stu-id="52db0-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="52db0-111">Para obtener más información y terminología, vea el tema [método icordebugprocess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .</span><span class="sxs-lookup"><span data-stu-id="52db0-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52db0-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="52db0-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52db0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52db0-113">Requirements</span></span>  
 <span data-ttu-id="52db0-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52db0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52db0-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52db0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52db0-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52db0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52db0-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52db0-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52db0-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="52db0-118">See also</span></span>

- [<span data-ttu-id="52db0-119">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="52db0-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="52db0-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="52db0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
