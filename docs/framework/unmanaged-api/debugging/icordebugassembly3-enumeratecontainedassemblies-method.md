---
description: 'Más información sobre: método icordebugassembly3:: EnumerateContainedAssemblies (método)'
title: Método ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 8933500713661ef785eb3ce5abc574e512580b6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754087"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="aa0e1-103">Método ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="aa0e1-103">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>

<span data-ttu-id="aa0e1-104">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa0e1-104">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa0e1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa0e1-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa0e1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa0e1-106">Parameters</span></span>  

 `ppAssemblies`  
 <span data-ttu-id="aa0e1-107">[out] Puntero a la dirección de un objeto de interfaz ICorDebugAssemblyEnum que es el enumerador.</span><span class="sxs-lookup"><span data-stu-id="aa0e1-107">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa0e1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aa0e1-108">Return Value</span></span>  

 <span data-ttu-id="aa0e1-109">`S_OK` si el objeto `ICorDebugAssembly3` es un contenedor; de lo contrario, `S_FALSE` y la enumeración está vacía.</span><span class="sxs-lookup"><span data-stu-id="aa0e1-109">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa0e1-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aa0e1-110">Remarks</span></span>  

 <span data-ttu-id="aa0e1-111">Se necesitan símbolos para enumerar los ensamblados contenidos.</span><span class="sxs-lookup"><span data-stu-id="aa0e1-111">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="aa0e1-112">Si no existen, el método devuelve `S_FALSE` y no se proporciona un enumerador válido.</span><span class="sxs-lookup"><span data-stu-id="aa0e1-112">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa0e1-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="aa0e1-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa0e1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa0e1-114">Requirements</span></span>  

 <span data-ttu-id="aa0e1-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa0e1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa0e1-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa0e1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa0e1-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa0e1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa0e1-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa0e1-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa0e1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa0e1-119">See also</span></span>

- [<span data-ttu-id="aa0e1-120">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="aa0e1-120">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="aa0e1-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="aa0e1-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
