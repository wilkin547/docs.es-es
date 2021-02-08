---
description: 'Más información acerca de: IMetaDataAssemblyImport:: FindAssembliesByName (método)'
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
ms.openlocfilehash: f9c25392cc2c70a0ebc17181b876cf9c6ba03c78
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789299"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="3c7bb-103">IMetaDataAssemblyImport::FindAssembliesByName (Método)</span><span class="sxs-lookup"><span data-stu-id="3c7bb-103">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>

<span data-ttu-id="3c7bb-104">Obtiene una matriz de ensamblados con el `szAssemblyName` parámetro especificado, utilizando las reglas estándar empleadas por el Common Language Runtime (CLR) para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-104">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c7bb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c7bb-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3c7bb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c7bb-106">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="3c7bb-107">de Directorio raíz en el que se va a buscar el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-107">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="3c7bb-108">Si este valor se establece en `null` , `FindAssembliesByName` solo buscará en la caché global de ensamblados el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-108">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="3c7bb-109">de Lista de subdirectorios delimitados por punto y coma (por ejemplo, "bin; bin2"), en el directorio raíz, en el que se va a buscar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-109">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="3c7bb-110">Estos directorios se sondean además de los especificados en las reglas de búsqueda predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-110">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="3c7bb-111">de Nombre del ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-111">[in] The name of the assembly to find.</span></span> <span data-ttu-id="3c7bb-112">El formato de esta cadena se define en la página de referencia de clase de <xref:System.Reflection.AssemblyName> .</span><span class="sxs-lookup"><span data-stu-id="3c7bb-112">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="3c7bb-113">de Matriz de tipo [IUnknown](/cpp/atl/iunknown) en la que se colocan los `IMetadataAssemblyImport` punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-113">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3c7bb-114">enuncia Número máximo de punteros de interfaz que se pueden colocar en `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="3c7bb-114">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="3c7bb-115">enuncia Número de punteros de interfaz devueltos.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-115">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="3c7bb-116">Es decir, el número de punteros de interfaz que se colocan realmente en `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="3c7bb-116">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c7bb-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3c7bb-117">Return Value</span></span>  
  
|<span data-ttu-id="3c7bb-118">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c7bb-118">HRESULT</span></span>|<span data-ttu-id="3c7bb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c7bb-119">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3c7bb-120">`FindAssembliesByName` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-120">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3c7bb-121">No hay ningún ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-121">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c7bb-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c7bb-122">Remarks</span></span>  

 <span data-ttu-id="3c7bb-123">Dado un nombre de ensamblado, el `FindAssembliesByName` método busca el ensamblado siguiendo las reglas estándar para resolver las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-123">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="3c7bb-124">(Para obtener más información, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../../deployment/how-the-runtime-locates-assemblies.md)). `FindAssembliesByName` permite al llamador configurar varios aspectos del contexto de la resolución de ensamblado, como la base de la aplicación y la ruta de acceso de búsqueda privada.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-124">(For more information, see [How the Runtime Locates Assemblies](../../deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="3c7bb-125">El `FindAssembliesByName` método requiere que se inicialice el CLR en el proceso para invocar la lógica de resolución de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-125">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="3c7bb-126">Por lo tanto, debe llamar a [coinicializar](../hosting/coinitializeee-function.md) (pasando COINITEE_DEFAULT) antes de llamar a `FindAssembliesByName` y después seguir con una llamada a [couninitializecor (](../hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="3c7bb-126">Therefore, you must call [CoInitializeEE](../hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="3c7bb-127">`FindAssembliesByName` Devuelve un puntero [IMetaDataImport](imetadataimport-interface.md) al archivo que contiene el manifiesto del ensamblado para el nombre de ensamblado que se pasa.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-127">`FindAssembliesByName` returns an [IMetaDataImport](imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="3c7bb-128">Si el nombre de ensamblado especificado no se especifica completamente (por ejemplo, si no incluye una versión), es posible que se devuelvan varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-128">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="3c7bb-129">`FindAssembliesByName` suele ser utilizado por un compilador que intenta buscar un ensamblado al que se hace referencia en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="3c7bb-129">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c7bb-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c7bb-130">Requirements</span></span>  

 <span data-ttu-id="3c7bb-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c7bb-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c7bb-132">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3c7bb-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c7bb-133">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c7bb-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c7bb-134">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c7bb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7bb-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c7bb-135">See also</span></span>

- [<span data-ttu-id="3c7bb-136">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="3c7bb-136">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="3c7bb-137">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c7bb-137">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
