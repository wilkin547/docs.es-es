---
description: 'Más información sobre: método icordebugprocess6:: EnableVirtualModuleSplitting (método)'
title: Método ICorDebugProcess6::EnableVirtualModuleSplitting
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: e56e66744ab971deba18f3bdc66d0cfb2053087f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722027"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a><span data-ttu-id="b28cf-103">Método ICorDebugProcess6::EnableVirtualModuleSplitting</span><span class="sxs-lookup"><span data-stu-id="b28cf-103">ICorDebugProcess6::EnableVirtualModuleSplitting Method</span></span>

<span data-ttu-id="b28cf-104">Habilita o deshabilita la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="b28cf-104">Enables or disables virtual module splitting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28cf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b28cf-105">Syntax</span></span>  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b28cf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b28cf-106">Parameters</span></span>  

 `enableSplitting`  
 <span data-ttu-id="b28cf-107">`true` para habilitar la división de módulos virtuales; `false` para deshabilitarla.</span><span class="sxs-lookup"><span data-stu-id="b28cf-107">`true` to enable virtual module splitting; `false` to disable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b28cf-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b28cf-108">Remarks</span></span>  

 <span data-ttu-id="b28cf-109">La división de módulos virtuales hace que [ICorDebug](icordebug-interface.md) reconozca los módulos que se combinaron durante el proceso de compilación y los presenta como un grupo de módulos independientes en lugar de un único módulo grande.</span><span class="sxs-lookup"><span data-stu-id="b28cf-109">Virtual module splitting causes [ICorDebug](icordebug-interface.md) to recognize modules that were merged together during the build process and present them as a group of separate modules rather than a single large module.</span></span> <span data-ttu-id="b28cf-110">Esto cambia el comportamiento de los diversos métodos [ICorDebug](icordebug-interface.md) descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="b28cf-110">Doing this changes the behavior of various [ICorDebug](icordebug-interface.md) methods described below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b28cf-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b28cf-111">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="b28cf-112">Puede llamar a este método y cambiar el valor de `enableSplitting` en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="b28cf-112">This method can be called and the value of `enableSplitting` can be changed at any time.</span></span> <span data-ttu-id="b28cf-113">No provoca ningún cambio funcional con estado en un objeto [ICorDebug](icordebug-interface.md) , a excepción de la modificación del comportamiento de los métodos enumerados en las secciones [División de módulos virtuales y API de depuración no administradas](#APIs) en el momento en que se llaman.</span><span class="sxs-lookup"><span data-stu-id="b28cf-113">It does not cause any stateful functional changes in an [ICorDebug](icordebug-interface.md) object, other than altering the behavior of the methods listed in the [Virtual module splitting and the unmanaged debugging APIs](#APIs) section at the time they are called.</span></span> <span data-ttu-id="b28cf-114">El uso de módulos virtuales hace que el rendimiento disminuya cuando se llama a estos métodos.</span><span class="sxs-lookup"><span data-stu-id="b28cf-114">Using virtual modules does incur a performance penalty when calling those methods.</span></span> <span data-ttu-id="b28cf-115">Además, es posible que se necesite un almacenamiento en caché considerable de los metadatos virtualizados para implementar correctamente las API de [IMetaDataImport](../metadata/imetadataimport-interface.md) , y estas cachés se pueden conservar incluso después de que se haya desactivado la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="b28cf-115">In addition, significant in-memory caching of the virtualized metadata may be required to correctly implement the [IMetaDataImport](../metadata/imetadataimport-interface.md) APIs, and these caches may be retained even after virtual module splitting has been turned off.</span></span>  
  
## <a name="terminology"></a><span data-ttu-id="b28cf-116">Terminología</span><span class="sxs-lookup"><span data-stu-id="b28cf-116">Terminology</span></span>  

 <span data-ttu-id="b28cf-117">Los siguientes términos sirven para describir la división de módulos virtuales:</span><span class="sxs-lookup"><span data-stu-id="b28cf-117">The following terms are used when describing virtual module splitting:</span></span>  
  
 <span data-ttu-id="b28cf-118">módulos de contenedor o contenedores</span><span class="sxs-lookup"><span data-stu-id="b28cf-118">container modules, or containers</span></span>  
 <span data-ttu-id="b28cf-119">Son los módulos agregados.</span><span class="sxs-lookup"><span data-stu-id="b28cf-119">The aggregate modules.</span></span>  
  
 <span data-ttu-id="b28cf-120">submódulos o módulos virtuales</span><span class="sxs-lookup"><span data-stu-id="b28cf-120">sub-modules, or virtual modules</span></span>  
 <span data-ttu-id="b28cf-121">Son los módulos incluidos en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="b28cf-121">The modules found in a container.</span></span>  
  
 <span data-ttu-id="b28cf-122">módulos regulares</span><span class="sxs-lookup"><span data-stu-id="b28cf-122">regular modules</span></span>  
 <span data-ttu-id="b28cf-123">Módulos que no se han combinado en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="b28cf-123">Modules that were not merged at build time.</span></span> <span data-ttu-id="b28cf-124">No son ni módulos de contenedor ni submódulos.</span><span class="sxs-lookup"><span data-stu-id="b28cf-124">They are neither container modules nor sub-modules.</span></span>  
  
 <span data-ttu-id="b28cf-125">Tanto los módulos de contenedor como los submódulos se representan mediante objetos de interfaz ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="b28cf-125">Both container modules and sub-modules are represented by ICorDebugModule interface objects.</span></span> <span data-ttu-id="b28cf-126">Sin embargo, el comportamiento de la interfaz es ligeramente diferente en cada caso, como \<x-ref to section> se describe en la sección.</span><span class="sxs-lookup"><span data-stu-id="b28cf-126">However, the behavior of the interface is slightly different in each case, as the \<x-ref to section> section describes.</span></span>  
  
## <a name="modules-and-assemblies"></a><span data-ttu-id="b28cf-127">Módulos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="b28cf-127">Modules and assemblies</span></span>  

 <span data-ttu-id="b28cf-128">En los escenarios donde se combinan ensamblados no se admiten ensamblados con varios módulos, por lo que hay una relación de uno a uno entre un módulo y un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b28cf-128">Multi-module assemblies are not supported for assembly merging scenarios, so there is a one-to-one relationship between a module and an assembly.</span></span> <span data-ttu-id="b28cf-129">Cada objeto ICorDebugModule, independientemente de si representa a un módulo de contenedor o a un submódulo, se corresponde con un objeto ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="b28cf-129">Each ICorDebugModule object, regardless of whether it represents a container module or a sub-module, has a corresponding ICorDebugAssembly object.</span></span> <span data-ttu-id="b28cf-130">El método [ICorDebugModule:: getassembly (](icordebugmodule-getassembly-method.md) convierte el módulo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b28cf-130">The [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method converts from the module to the assembly.</span></span> <span data-ttu-id="b28cf-131">Para asignar en la otra dirección, el método [ICorDebugAssembly:: enumeratemodules (](icordebugassembly-enumeratemodules-method.md) solo enumera 1 módulo.</span><span class="sxs-lookup"><span data-stu-id="b28cf-131">To map in the other direction, the [ICorDebugAssembly::EnumerateModules](icordebugassembly-enumeratemodules-method.md) method enumerates only 1 module.</span></span> <span data-ttu-id="b28cf-132">Dado que ensamblado y módulo conforman un par estrechamente unido en este caso, los términos módulo y ensamblado se han convertido en prácticamente intercambiables.</span><span class="sxs-lookup"><span data-stu-id="b28cf-132">Because assembly and module form a tightly coupled pair in this case, the terms assembly and module become largely interchangeable.</span></span>  
  
## <a name="behavioral-differences"></a><span data-ttu-id="b28cf-133">Diferencias de comportamiento</span><span class="sxs-lookup"><span data-stu-id="b28cf-133">Behavioral differences</span></span>  

 <span data-ttu-id="b28cf-134">Los módulos del contenedor tienen los siguientes comportamientos y características:</span><span class="sxs-lookup"><span data-stu-id="b28cf-134">Container modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="b28cf-135">Sus metadatos para todos los submódulos que lo conforman se combinan entre sí.</span><span class="sxs-lookup"><span data-stu-id="b28cf-135">Their metadata for all of the constituent sub-modules is merged together.</span></span>  
  
- <span data-ttu-id="b28cf-136">Sus nombres de tipo se pueden alterar.</span><span class="sxs-lookup"><span data-stu-id="b28cf-136">Their type names may be mangled.</span></span>  
  
- <span data-ttu-id="b28cf-137">El método [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) devuelve la ruta de acceso a un módulo en disco.</span><span class="sxs-lookup"><span data-stu-id="b28cf-137">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the path to an on-disk module.</span></span>  
  
- <span data-ttu-id="b28cf-138">El método [ICorDebugModule::FUL](icordebugmodule-getsize-method.md) devuelve el tamaño de la imagen.</span><span class="sxs-lookup"><span data-stu-id="b28cf-138">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the size of that image.</span></span>  
  
- <span data-ttu-id="b28cf-139">El método ICorDebugAssembly3.EnumerateContainedAssemblies enumera los submódulos.</span><span class="sxs-lookup"><span data-stu-id="b28cf-139">The ICorDebugAssembly3.EnumerateContainedAssemblies method lists the sub-modules.</span></span>  
  
- <span data-ttu-id="b28cf-140">El método ICorDebugAssembly3.GetContainerAssembly devuelve `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-140">The ICorDebugAssembly3.GetContainerAssembly method returns `S_FALSE`.</span></span>  
  
 <span data-ttu-id="b28cf-141">Los submódulos tienen los siguientes comportamientos y características:</span><span class="sxs-lookup"><span data-stu-id="b28cf-141">Sub-modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="b28cf-142">Tienen un conjunto reducido de metadatos que corresponde únicamente al ensamblado original que se ha combinado.</span><span class="sxs-lookup"><span data-stu-id="b28cf-142">They have a reduced set of metadata that corresponds only to the original assembly that was merged.</span></span>  
  
- <span data-ttu-id="b28cf-143">Los nombres de los metadatos no se alteran.</span><span class="sxs-lookup"><span data-stu-id="b28cf-143">The metadata names are not mangled.</span></span>  
  
- <span data-ttu-id="b28cf-144">Es improbable que los tokens de los metadatos coincidan con los tokens del ensamblado original antes de que combinarse en el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="b28cf-144">Metadata tokens are unlikely to match the tokens in the original assembly before it was merged in the build process.</span></span>  
  
- <span data-ttu-id="b28cf-145">El método [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) devuelve el nombre del ensamblado, no una ruta de acceso del archivo.</span><span class="sxs-lookup"><span data-stu-id="b28cf-145">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the assembly name, not a file path.</span></span>  
  
- <span data-ttu-id="b28cf-146">El método [ICorDebugModule::FUL](icordebugmodule-getsize-method.md) devuelve el tamaño original de la imagen sin combinar.</span><span class="sxs-lookup"><span data-stu-id="b28cf-146">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the original unmerged image size.</span></span>  
  
- <span data-ttu-id="b28cf-147">El método ICorDebugModule3.EnumerateContainedAssemblies devuelve `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="b28cf-147">The ICorDebugModule3.EnumerateContainedAssemblies method returns `S_FALSE`.</span></span>  
  
- <span data-ttu-id="b28cf-148">El método ICorDebugAssembly3.GetContainerAssembly devuelve el módulo contenedor.</span><span class="sxs-lookup"><span data-stu-id="b28cf-148">The ICorDebugAssembly3.GetContainerAssembly method returns the containing module.</span></span>  
  
## <a name="interfaces-retrieved-from-modules"></a><span data-ttu-id="b28cf-149">Interfaces obtenidas de los módulos</span><span class="sxs-lookup"><span data-stu-id="b28cf-149">Interfaces retrieved from modules</span></span>  

 <span data-ttu-id="b28cf-150">Se pueden crear y recuperar diversas interfaces de los módulos.</span><span class="sxs-lookup"><span data-stu-id="b28cf-150">A variety of interfaces can be created or retrieved from modules.</span></span> <span data-ttu-id="b28cf-151">Algunas son:</span><span class="sxs-lookup"><span data-stu-id="b28cf-151">Some of these include:</span></span>  
  
- <span data-ttu-id="b28cf-152">Un objeto ICorDebugClass, devuelto por el método [ICorDebugModule:: GetClassFromToken (](icordebugmodule-getclassfromtoken-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b28cf-152">An ICorDebugClass object, which is returned by the [ICorDebugModule::GetClassFromToken](icordebugmodule-getclassfromtoken-method.md) method.</span></span>  
  
- <span data-ttu-id="b28cf-153">Un objeto ICorDebugAssembly, devuelto por el método [ICorDebugModule:: getassembly (](icordebugmodule-getassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b28cf-153">An ICorDebugAssembly object, which is returned by the [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method.</span></span>  
  
 <span data-ttu-id="b28cf-154">Este tipo de objetos siempre se almacenan en caché por [ICorDebug](icordebug-interface.md)y tendrán la misma identidad de puntero independientemente de si se crearon o consultaron desde el módulo contenedor o un submódulo.</span><span class="sxs-lookup"><span data-stu-id="b28cf-154">These objects are always cached by [ICorDebug](icordebug-interface.md), and they will have the same pointer identity regardless of whether they were created or queried from the container module or a sub-module.</span></span> <span data-ttu-id="b28cf-155">El submódulo proporciona una vista filtrada de estos objetos en caché, no una memoria caché independiente con sus propias copias.</span><span class="sxs-lookup"><span data-stu-id="b28cf-155">The sub-module provides a filtered view of these cached objects, not a separate cache with its own copies.</span></span>  
  
<a name="APIs"></a>

## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a><span data-ttu-id="b28cf-156">División de módulos virtuales y API de depuración no administradas</span><span class="sxs-lookup"><span data-stu-id="b28cf-156">Virtual module splitting and the unmanaged debugging APIs</span></span>  

 <span data-ttu-id="b28cf-157">En la siguiente tabla se muestra cómo la división de módulos virtuales afecta al comportamiento de otros métodos en una API de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="b28cf-157">The following table shows how virtual module splitting affects the behavior of other methods in the unmanaged debugging API.</span></span>  
  
|<span data-ttu-id="b28cf-158">Método</span><span class="sxs-lookup"><span data-stu-id="b28cf-158">Method</span></span>|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[<span data-ttu-id="b28cf-159">ICorDebugFunction::GetModule</span><span class="sxs-lookup"><span data-stu-id="b28cf-159">ICorDebugFunction::GetModule</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="b28cf-160">Devuelve el submódulo en el que esta función se definió originalmente.</span><span class="sxs-lookup"><span data-stu-id="b28cf-160">Returns the sub-module this function was originally defined in</span></span>|<span data-ttu-id="b28cf-161">Devuelve el módulo contenedor con el que esta función se combinó.</span><span class="sxs-lookup"><span data-stu-id="b28cf-161">Returns the container module this function was merged into</span></span>|  
|[<span data-ttu-id="b28cf-162">ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="b28cf-162">ICorDebugClass::GetModule</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="b28cf-163">Devuelve el submódulo en el que esta clase se definió originalmente.</span><span class="sxs-lookup"><span data-stu-id="b28cf-163">Returns the sub-module this class was originally defined in.</span></span>|<span data-ttu-id="b28cf-164">Devuelve el módulo contenedor con el que esta clase se combinó.</span><span class="sxs-lookup"><span data-stu-id="b28cf-164">Returns the container module this class was merged into.</span></span>|  
|<span data-ttu-id="b28cf-165">ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="b28cf-165">ICorDebugModuleDebugEvent::GetModule</span></span>|<span data-ttu-id="b28cf-166">Devuelve el módulo contenedor que se cargó.</span><span class="sxs-lookup"><span data-stu-id="b28cf-166">Returns the container module that was loaded.</span></span> <span data-ttu-id="b28cf-167">Los submódulos no tienen eventos load, independientemente de esta configuración.</span><span class="sxs-lookup"><span data-stu-id="b28cf-167">Sub-modules are not given load events regardless of this setting.</span></span>|<span data-ttu-id="b28cf-168">Devuelve el módulo contenedor que se cargó.</span><span class="sxs-lookup"><span data-stu-id="b28cf-168">Returns the container module that was loaded.</span></span>|  
|[<span data-ttu-id="b28cf-169">ICorDebugAppDomain::EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="b28cf-169">ICorDebugAppDomain::EnumerateAssemblies</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="b28cf-170">Devuelve una lista de los subensamblados y ensamblados regulares; no se incluyen ensamblados de contenedor.</span><span class="sxs-lookup"><span data-stu-id="b28cf-170">Returns a list of sub-assemblies and regular assemblies; no container assemblies are included.</span></span> <span data-ttu-id="b28cf-171">**Nota:**  Si faltan símbolos en algún ensamblado de contenedor, no se enumerará ninguno de sus Subensamblados.</span><span class="sxs-lookup"><span data-stu-id="b28cf-171">**Note:**  If any container assembly is missing symbols, none of its sub-assemblies will be enumerated.</span></span> <span data-ttu-id="b28cf-172">Si faltan símbolos en algún ensamblado regular, puede que se enumere o no.</span><span class="sxs-lookup"><span data-stu-id="b28cf-172">If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|<span data-ttu-id="b28cf-173">Devuelve una lista de ensamblados de contenedor y ensamblados regulares; no se incluyen subensamblados.</span><span class="sxs-lookup"><span data-stu-id="b28cf-173">Returns a list of container assemblies and regular assemblies; no sub-assemblies are included.</span></span> <span data-ttu-id="b28cf-174">**Nota:**  Si faltan símbolos en algún ensamblado normal, se puede enumerar o no.</span><span class="sxs-lookup"><span data-stu-id="b28cf-174">**Note:**  If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|  
|<span data-ttu-id="b28cf-175">[ICorDebugCode:: getCode](icordebugcode-getcode-method.md) (solo cuando se hace referencia a código Il)</span><span class="sxs-lookup"><span data-stu-id="b28cf-175">[ICorDebugCode::GetCode](icordebugcode-getcode-method.md) (when referring to IL code only)</span></span>|<span data-ttu-id="b28cf-176">Devuelve el código IL que sería válido en una imagen de ensamblado antes de la fusión mediante combinación.</span><span class="sxs-lookup"><span data-stu-id="b28cf-176">Returns IL that would be valid in a pre-merge assembly image.</span></span> <span data-ttu-id="b28cf-177">En concreto, cualquier token de metadatos en línea será correctamente un token TypeRef o MemberRef cuando los tipos a los que se hace referencia no están definidos en el módulo virtual que contiene el IL.</span><span class="sxs-lookup"><span data-stu-id="b28cf-177">Specifically, any inline metadata tokens will correctly be TypeRef or MemberRef tokens when the types being referred to are not defined in the virtual module containing the IL.</span></span> <span data-ttu-id="b28cf-178">Estos tokens TypeRef o MemberRef se pueden buscar en el objeto [IMetaDataImport](../metadata/imetadataimport-interface.md) del objeto ICorDebugModule virtual correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b28cf-178">These TypeRef or MemberRef tokens can be looked up in the [IMetaDataImport](../metadata/imetadataimport-interface.md) object for the corresponding virtual ICorDebugModule object.</span></span>|<span data-ttu-id="b28cf-179">Devuelve el IL de la imagen de ensamblado posterior a la combinación.</span><span class="sxs-lookup"><span data-stu-id="b28cf-179">Returns the IL in the post-merge assembly image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b28cf-180">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b28cf-180">Requirements</span></span>  

 <span data-ttu-id="b28cf-181">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b28cf-181">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28cf-182">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b28cf-182">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b28cf-183">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b28cf-183">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b28cf-184">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28cf-184">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28cf-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="b28cf-185">See also</span></span>

- [<span data-ttu-id="b28cf-186">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="b28cf-186">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="b28cf-187">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b28cf-187">Debugging Interfaces</span></span>](debugging-interfaces.md)
