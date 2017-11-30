---
title: ICorDebugSymbolProvider (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96f5d897b1f426fd85fd274d5e56e8726b8cb892
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="de42b-102">ICorDebugSymbolProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="de42b-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="de42b-103">Proporciona métodos que pueden usarse para recuperar información de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="de42b-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de42b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="de42b-104">Methods</span></span>  
  
|<span data-ttu-id="de42b-105">Método</span><span class="sxs-lookup"><span data-stu-id="de42b-105">Method</span></span>|<span data-ttu-id="de42b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="de42b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de42b-107">GetAssemblyImageBytes (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-107">GetAssemblyImageBytes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="de42b-108">Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) en el ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="de42b-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="de42b-109">GetAssemblyImageMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-109">GetAssemblyImageMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="de42b-110">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="de42b-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="de42b-111">GetCodeRange (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-111">GetCodeRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="de42b-112">Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="de42b-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="de42b-113">GetInstanceFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-113">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="de42b-114">Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="de42b-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="de42b-115">GetMergedAssemblyRecords (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-115">GetMergedAssemblyRecords Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="de42b-116">Obtiene los registros de símbolos para todos los ensamblados combinados.</span><span class="sxs-lookup"><span data-stu-id="de42b-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="de42b-117">GetMethodLocalSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-117">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="de42b-118">Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="de42b-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="de42b-119">GetMethodParameterSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-119">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="de42b-120">Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="de42b-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="de42b-121">GetMethodProps (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="de42b-122">Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.</span><span class="sxs-lookup"><span data-stu-id="de42b-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="de42b-123">GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-123">GetObjectSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="de42b-124">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="de42b-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="de42b-125">GetStaticFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-125">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="de42b-126">Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="de42b-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="de42b-127">GetTypeProps (método)</span><span class="sxs-lookup"><span data-stu-id="de42b-127">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="de42b-128">Devuelve información acerca de las propiedades de un tipo, como el número de firmas de sus parámetros genéricos, dada una dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="de42b-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de42b-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de42b-129">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de42b-130">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="de42b-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="de42b-131">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="de42b-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de42b-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de42b-132">Requirements</span></span>  
 <span data-ttu-id="de42b-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de42b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de42b-134">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de42b-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de42b-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de42b-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de42b-136">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de42b-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de42b-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="de42b-137">See Also</span></span>  
 [<span data-ttu-id="de42b-138">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="de42b-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="de42b-139">Depuración</span><span class="sxs-lookup"><span data-stu-id="de42b-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
