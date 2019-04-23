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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b388dae0f109ff366f83c92de99b00b80bcc01a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108724"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="bd58c-102">IMetaDataAssemblyImport::FindAssembliesByName (Método)</span><span class="sxs-lookup"><span data-stu-id="bd58c-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="bd58c-103">Obtiene una matriz de ensamblados con los valores especificados `szAssemblyName` parámetro, utilizando las reglas estándares empleadas por common language runtime (CLR) para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="bd58c-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd58c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd58c-104">Syntax</span></span>  
  
```  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd58c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd58c-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="bd58c-106">[in] El directorio raíz en el que se va a buscar el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="bd58c-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="bd58c-107">Si este valor se establece en `null`, `FindAssembliesByName` buscará solo en la caché global de ensamblados para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bd58c-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="bd58c-108">[in] Una lista de los subdirectorios delimitada por punto y coma (por ejemplo, "bin; bin2"), en el directorio raíz, en el que se va a buscar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bd58c-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="bd58c-109">Además de aquéllos especificados en las reglas de sondeo predeterminado se busca en estos directorios.</span><span class="sxs-lookup"><span data-stu-id="bd58c-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="bd58c-110">[in] El nombre del ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="bd58c-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="bd58c-111">El formato de esta cadena se define en la página de referencia de clase para <xref:System.Reflection.AssemblyName>.</span><span class="sxs-lookup"><span data-stu-id="bd58c-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="bd58c-112">[in] Una matriz de tipo [IUnknown](/cpp/atl/iunknown) en el que se va a colocar el `IMetadataAssemblyImport` punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="bd58c-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bd58c-113">[out] El número máximo de punteros de interfaz que se pueden colocar en `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="bd58c-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="bd58c-114">[out] Devuelve el número de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="bd58c-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="bd58c-115">Es decir, el número de punteros de interfaz realmente colocados en `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="bd58c-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd58c-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bd58c-116">Return Value</span></span>  
  
|<span data-ttu-id="bd58c-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd58c-117">HRESULT</span></span>|<span data-ttu-id="bd58c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd58c-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bd58c-119">`FindAssembliesByName` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd58c-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bd58c-120">No hay ningún ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bd58c-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd58c-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd58c-121">Remarks</span></span>  
 <span data-ttu-id="bd58c-122">Asigna un nombre de ensamblado, el `FindAssembliesByName` método encuentra el ensamblado siguiendo las reglas estándar para resolver las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bd58c-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="bd58c-123">(Para obtener más información, consulte [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` permite al llamador configurar varios aspectos del contexto de resolución de ensamblado, como la ruta de acceso de búsqueda privada y base de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bd58c-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="bd58c-124">El `FindAssembliesByName` método requiere que se puede inicializar en el proceso para invocar la lógica de resolución de ensamblado CLR.</span><span class="sxs-lookup"><span data-stu-id="bd58c-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="bd58c-125">Por lo tanto, debe llamar a [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (pasando COINITEE_DEFAULT) antes de llamar a `FindAssembliesByName`y, a continuación, siga con una llamada a [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="bd58c-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="bd58c-126">`FindAssembliesByName` Devuelve un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) puntero en el archivo que contiene el manifiesto del ensamblado para el nombre del ensamblado que se pasa.</span><span class="sxs-lookup"><span data-stu-id="bd58c-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="bd58c-127">Si el nombre del ensamblado no se especifica completamente (por ejemplo, si no tiene una versión), se podrían devolver varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="bd58c-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="bd58c-128">`FindAssembliesByName` se utiliza normalmente mediante un compilador que intenta encontrar un ensamblado que se hace referencia en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="bd58c-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd58c-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd58c-129">Requirements</span></span>  
 <span data-ttu-id="bd58c-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd58c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd58c-131">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd58c-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd58c-132">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd58c-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd58c-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd58c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd58c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd58c-134">See also</span></span>

- [<span data-ttu-id="bd58c-135">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="bd58c-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="bd58c-136">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd58c-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
