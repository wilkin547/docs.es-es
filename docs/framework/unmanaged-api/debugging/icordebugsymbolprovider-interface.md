---
description: 'Más información acerca de: interfaz ICorDebugSymbolProvider'
title: Interfaz ICorDebugSymbolProvider
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: bd47f294092ee87fc1f34bc68fe744b447e21f20
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659587"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="649ef-103">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="649ef-103">ICorDebugSymbolProvider Interface</span></span>

<span data-ttu-id="649ef-104">Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="649ef-104">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="649ef-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="649ef-105">Methods</span></span>  
  
|<span data-ttu-id="649ef-106">Método</span><span class="sxs-lookup"><span data-stu-id="649ef-106">Method</span></span>|<span data-ttu-id="649ef-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="649ef-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="649ef-108">Método GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="649ef-108">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="649ef-109">Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="649ef-109">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="649ef-110">Método GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="649ef-110">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="649ef-111">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="649ef-111">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="649ef-112">Método GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="649ef-112">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="649ef-113">Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="649ef-113">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="649ef-114">Método GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="649ef-114">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="649ef-115">Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="649ef-115">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="649ef-116">Método GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="649ef-116">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="649ef-117">Obtiene los registros de símbolos para todos los ensamblados combinados.</span><span class="sxs-lookup"><span data-stu-id="649ef-117">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="649ef-118">Método GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="649ef-118">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="649ef-119">Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="649ef-119">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="649ef-120">Método GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="649ef-120">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="649ef-121">Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="649ef-121">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="649ef-122">GetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="649ef-122">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="649ef-123">Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.</span><span class="sxs-lookup"><span data-stu-id="649ef-123">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="649ef-124">Método GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="649ef-124">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="649ef-125">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="649ef-125">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="649ef-126">Método GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="649ef-126">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="649ef-127">Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="649ef-127">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="649ef-128">Método GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="649ef-128">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="649ef-129">Devuelve información acerca de las propiedades de un tipo, como el número de firmas de sus parámetros genéricos, dada una dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="649ef-129">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="649ef-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="649ef-130">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="649ef-131">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="649ef-131">This interface is available with .NET Native only.</span></span> <span data-ttu-id="649ef-132">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="649ef-132">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="649ef-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="649ef-133">Requirements</span></span>  

 <span data-ttu-id="649ef-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="649ef-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="649ef-135">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="649ef-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="649ef-136">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="649ef-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="649ef-137">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="649ef-137">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="649ef-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="649ef-138">See also</span></span>

- [<span data-ttu-id="649ef-139">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="649ef-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="649ef-140">Depuración</span><span class="sxs-lookup"><span data-stu-id="649ef-140">Debugging</span></span>](index.md)
