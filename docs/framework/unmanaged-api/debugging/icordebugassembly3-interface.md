---
description: 'Más información acerca de: interfaz método icordebugassembly3'
title: Interfaz ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 3a8cabf41dffa75d82c2b6fde53dff2ede4838e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791509"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="eef5e-103">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="eef5e-103">ICorDebugAssembly3 Interface</span></span>

<span data-ttu-id="eef5e-104">Extiende la interfaz ICorDebugAssembly de manera lógica para proporcionar compatibilidad con los ensamblados de contenedor y con los ensamblados que estos contienen.</span><span class="sxs-lookup"><span data-stu-id="eef5e-104">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eef5e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="eef5e-105">Methods</span></span>  
  
|<span data-ttu-id="eef5e-106">Método</span><span class="sxs-lookup"><span data-stu-id="eef5e-106">Method</span></span>|<span data-ttu-id="eef5e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="eef5e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eef5e-108">Método EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="eef5e-108">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="eef5e-109">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="eef5e-109">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="eef5e-110">Método GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="eef5e-110">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="eef5e-111">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="eef5e-111">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eef5e-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eef5e-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eef5e-113">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="eef5e-113">The interface is available with .NET Native only.</span></span> <span data-ttu-id="eef5e-114">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="eef5e-114">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eef5e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eef5e-115">Requirements</span></span>  

 <span data-ttu-id="eef5e-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eef5e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eef5e-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eef5e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eef5e-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eef5e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eef5e-119">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eef5e-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef5e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="eef5e-120">See also</span></span>

- [<span data-ttu-id="eef5e-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="eef5e-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="eef5e-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="eef5e-122">Debugging</span></span>](index.md)
