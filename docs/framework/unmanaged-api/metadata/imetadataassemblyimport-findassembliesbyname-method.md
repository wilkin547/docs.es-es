---
title: IMetaDataAssemblyImport::FindAssembliesByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177800"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="644b5-102">IMetaDataAssemblyImport::FindAssembliesByName (Método)</span><span class="sxs-lookup"><span data-stu-id="644b5-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="644b5-103">Obtiene una matriz de ensamblados `szAssemblyName` con el parámetro especificado, utilizando las reglas estándar empleadas por Common Language Runtime (CLR) para resolver referencias.</span><span class="sxs-lookup"><span data-stu-id="644b5-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="644b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="644b5-104">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,
    [in]  LPCWSTR     szPrivateBin,
    [in]  LPCWSTR     szAssemblyName,
    [out] IUnknown    *ppIUnk[],
    [in]  ULONG       cMax,
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="644b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="644b5-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="644b5-106">[en] El directorio raíz en el que se va a buscar el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="644b5-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="644b5-107">Si este valor `null`se `FindAssembliesByName` establece en , buscará solo en la caché global de ensamblados para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="644b5-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="644b5-108">[en] Una lista de subdirectorios delimitados por punto y coma (por ejemplo, "bin;bin2"), en el directorio raíz, en el que buscar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="644b5-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="644b5-109">Estos directorios se sondean además de los especificados en las reglas de sondeo predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="644b5-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="644b5-110">[en] El nombre del ensamblado que se ha de buscar.</span><span class="sxs-lookup"><span data-stu-id="644b5-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="644b5-111">El formato de esta cadena se define <xref:System.Reflection.AssemblyName>en la página de referencia de clase para .</span><span class="sxs-lookup"><span data-stu-id="644b5-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="644b5-112">[en] Matriz de tipo [IUnknown](/cpp/atl/iunknown) en `IMetadataAssemblyImport` la que se colocan los punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="644b5-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="644b5-113">[fuera] El número máximo de punteros de `ppIUnk`interfaz que se pueden colocar en .</span><span class="sxs-lookup"><span data-stu-id="644b5-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="644b5-114">[fuera] El número de punteros de interfaz devueltos.</span><span class="sxs-lookup"><span data-stu-id="644b5-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="644b5-115">Es decir, el número de punteros de interfaz colocados en `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="644b5-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="644b5-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="644b5-116">Return Value</span></span>  
  
|<span data-ttu-id="644b5-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="644b5-117">HRESULT</span></span>|<span data-ttu-id="644b5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="644b5-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="644b5-119">`FindAssembliesByName`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="644b5-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="644b5-120">No hay ensamblados.</span><span class="sxs-lookup"><span data-stu-id="644b5-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="644b5-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="644b5-121">Remarks</span></span>  
 <span data-ttu-id="644b5-122">Dado un nombre `FindAssembliesByName` de ensamblado, el método busca el ensamblado siguiendo las reglas estándar para resolver referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="644b5-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="644b5-123">(Para obtener más información, consulte cómo el motor en tiempo de [ejecución localiza ensamblados](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` permite al autor de la llamada configurar varios aspectos del contexto de resolución de ensamblado, como la base de aplicaciones y la ruta de búsqueda privada.</span><span class="sxs-lookup"><span data-stu-id="644b5-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="644b5-124">El `FindAssembliesByName` método requiere que CLR se inicialice en el proceso para invocar la lógica de resolución de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="644b5-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="644b5-125">Por lo tanto, debe llamar a [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (pasando COINITEE_DEFAULT) antes de llamar `FindAssembliesByName`y, a continuación, seguir con una llamada a [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="644b5-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="644b5-126">`FindAssembliesByName`devuelve un [puntero IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) al archivo que contiene el manifiesto del ensamblado para el nombre del ensamblado que se pasa.</span><span class="sxs-lookup"><span data-stu-id="644b5-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="644b5-127">Si el nombre de ensamblado especificado no se especifica completamente (por ejemplo, si no incluye una versión), es posible que se devuelvan varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="644b5-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="644b5-128">`FindAssembliesByName`normalmente se usa un compilador que intenta encontrar un ensamblado al que se hace referencia en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="644b5-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="644b5-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="644b5-129">Requirements</span></span>  
 <span data-ttu-id="644b5-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="644b5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="644b5-131">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="644b5-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="644b5-132">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="644b5-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="644b5-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="644b5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="644b5-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="644b5-134">See also</span></span>

- [<span data-ttu-id="644b5-135">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="644b5-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="644b5-136">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="644b5-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
