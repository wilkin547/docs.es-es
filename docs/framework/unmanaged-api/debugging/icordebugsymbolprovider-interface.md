---
title: Interfaz ICorDebugSymbolProvider
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: ff1f39be3d3db43f70cfa4a0711a3f42c180bc1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672089"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="01b50-102">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="01b50-102">ICorDebugSymbolProvider Interface</span></span>

<span data-ttu-id="01b50-103">Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="01b50-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01b50-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="01b50-104">Methods</span></span>  
  
|<span data-ttu-id="01b50-105">Método</span><span class="sxs-lookup"><span data-stu-id="01b50-105">Method</span></span>|<span data-ttu-id="01b50-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="01b50-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01b50-107">Método GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="01b50-107">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="01b50-108">Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="01b50-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="01b50-109">Método GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="01b50-109">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="01b50-110">Devuelve los metadatos desde un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="01b50-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="01b50-111">Método GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="01b50-111">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="01b50-112">Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.</span><span class="sxs-lookup"><span data-stu-id="01b50-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="01b50-113">Método GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="01b50-113">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="01b50-114">Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="01b50-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="01b50-115">Método GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="01b50-115">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="01b50-116">Obtiene los registros de símbolos para todos los ensamblados combinados.</span><span class="sxs-lookup"><span data-stu-id="01b50-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="01b50-117">Método GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="01b50-117">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="01b50-118">Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="01b50-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="01b50-119">Método GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="01b50-119">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="01b50-120">Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="01b50-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="01b50-121">Método GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="01b50-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="01b50-122">Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.</span><span class="sxs-lookup"><span data-stu-id="01b50-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="01b50-123">GetObjectSize (Método)</span><span class="sxs-lookup"><span data-stu-id="01b50-123">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="01b50-124">Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="01b50-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="01b50-125">Método GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="01b50-125">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="01b50-126">Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="01b50-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="01b50-127">Método GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="01b50-127">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="01b50-128">Devuelve información acerca de las propiedades de un tipo, como el número de firmas de sus parámetros genéricos, dada una dirección virtual relativa (RVA) en una tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="01b50-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01b50-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01b50-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01b50-130">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="01b50-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="01b50-131">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="01b50-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01b50-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01b50-132">Requirements</span></span>  

 <span data-ttu-id="01b50-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01b50-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01b50-134">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01b50-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01b50-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01b50-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01b50-136">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01b50-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b50-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01b50-137">See also</span></span>

- [<span data-ttu-id="01b50-138">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="01b50-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="01b50-139">Depuración</span><span class="sxs-lookup"><span data-stu-id="01b50-139">Debugging</span></span>](index.md)
