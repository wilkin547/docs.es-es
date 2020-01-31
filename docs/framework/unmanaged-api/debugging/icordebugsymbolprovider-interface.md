---
title: ICorDebugSymbolProvider (Interfaz)
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: 6f7a8a2b12c047b956a3b6e85fe8365e0360b3f2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791529"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="e43bc-102">ICorDebugSymbolProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e43bc-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="e43bc-103">Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="e43bc-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e43bc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e43bc-104">Methods</span></span>  
  
|<span data-ttu-id="e43bc-105">Método</span><span class="sxs-lookup"><span data-stu-id="e43bc-105">Method</span></span>|<span data-ttu-id="e43bc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e43bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e43bc-107">GetAssemblyImageBytes (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-107">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="e43bc-108">Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="e43bc-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="e43bc-109">GetAssemblyImageMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-109">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="e43bc-110">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="e43bc-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="e43bc-111">GetCodeRange (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-111">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="e43bc-112">Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="e43bc-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="e43bc-113">GetInstanceFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-113">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="e43bc-114">Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="e43bc-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="e43bc-115">GetMergedAssemblyRecords (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-115">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="e43bc-116">Obtiene los registros de símbolos para todos los ensamblados combinados.</span><span class="sxs-lookup"><span data-stu-id="e43bc-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="e43bc-117">GetMethodLocalSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-117">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="e43bc-118">Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="e43bc-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="e43bc-119">GetMethodParameterSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-119">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="e43bc-120">Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="e43bc-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="e43bc-121">GetMethodProps (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="e43bc-122">Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.</span><span class="sxs-lookup"><span data-stu-id="e43bc-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="e43bc-123">GetObjectSize (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-123">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="e43bc-124">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="e43bc-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="e43bc-125">GetStaticFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-125">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="e43bc-126">Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="e43bc-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="e43bc-127">GetTypeProps (método)</span><span class="sxs-lookup"><span data-stu-id="e43bc-127">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="e43bc-128">Devuelve información acerca de las propiedades de un tipo, como el número de firmas de sus parámetros genéricos, dada una dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="e43bc-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e43bc-129">Notas</span><span class="sxs-lookup"><span data-stu-id="e43bc-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e43bc-130">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e43bc-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e43bc-131">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="e43bc-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e43bc-132">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e43bc-132">Requirements</span></span>  
 <span data-ttu-id="e43bc-133">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e43bc-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e43bc-134">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e43bc-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e43bc-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e43bc-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e43bc-136">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e43bc-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43bc-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="e43bc-137">See also</span></span>

- [<span data-ttu-id="e43bc-138">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e43bc-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e43bc-139">Depuración</span><span class="sxs-lookup"><span data-stu-id="e43bc-139">Debugging</span></span>](index.md)
