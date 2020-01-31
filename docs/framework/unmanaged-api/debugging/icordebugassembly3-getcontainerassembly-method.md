---
title: Método ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 969cca6d5613670fc4b26fc973785b4874c3684c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778068"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="84282-102">Método ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="84282-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="84282-103">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="84282-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84282-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84282-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84282-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="84282-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="84282-106">Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado de contenedor, o **null** si se produce un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="84282-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84282-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="84282-107">Return Value</span></span>  
 <span data-ttu-id="84282-108">`S_OK` si la llamada al método se realiza correctamente; de lo contrario, `S_FALSE`y `ppAssembly` es **null**.</span><span class="sxs-lookup"><span data-stu-id="84282-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84282-109">Notas</span><span class="sxs-lookup"><span data-stu-id="84282-109">Remarks</span></span>  
 <span data-ttu-id="84282-110">Si este ensamblado se ha combinado con otros dentro de un solo ensamblado de contenedor, este método devuelve el ensamblado de contenedor.</span><span class="sxs-lookup"><span data-stu-id="84282-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="84282-111">Para obtener más información y terminología, vea el tema [método icordebugprocess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .</span><span class="sxs-lookup"><span data-stu-id="84282-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84282-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="84282-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84282-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="84282-113">Requirements</span></span>  
 <span data-ttu-id="84282-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84282-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84282-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84282-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84282-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84282-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84282-117">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84282-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84282-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="84282-118">See also</span></span>

- [<span data-ttu-id="84282-119">ICorDebugAssembly3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84282-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="84282-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="84282-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
