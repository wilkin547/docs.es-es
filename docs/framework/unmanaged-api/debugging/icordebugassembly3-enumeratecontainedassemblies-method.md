---
title: Método ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ccb52468a530280527252e0e0c43cc9edbb2c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080961"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="107c2-102">Método ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="107c2-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="107c2-103">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="107c2-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="107c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="107c2-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="107c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="107c2-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="107c2-106">[out] Un puntero a la dirección de un objeto de interfaz ICorDebugAssemblyEnum que es el enumerador.</span><span class="sxs-lookup"><span data-stu-id="107c2-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="107c2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="107c2-107">Return Value</span></span>  
 <span data-ttu-id="107c2-108">`S_OK` si el objeto `ICorDebugAssembly3` es un contenedor; de lo contrario, `S_FALSE` y la enumeración está vacía.</span><span class="sxs-lookup"><span data-stu-id="107c2-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="107c2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="107c2-109">Remarks</span></span>  
 <span data-ttu-id="107c2-110">Se necesitan símbolos para enumerar los ensamblados contenidos.</span><span class="sxs-lookup"><span data-stu-id="107c2-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="107c2-111">Si no existen, el método devuelve `S_FALSE` y no se proporciona un enumerador válido.</span><span class="sxs-lookup"><span data-stu-id="107c2-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="107c2-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="107c2-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="107c2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="107c2-113">Requirements</span></span>  
 <span data-ttu-id="107c2-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="107c2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="107c2-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="107c2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="107c2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="107c2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="107c2-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="107c2-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="107c2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="107c2-118">See also</span></span>

- [<span data-ttu-id="107c2-119">ICorDebugAssembly3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="107c2-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="107c2-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="107c2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
