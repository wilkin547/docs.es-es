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
ms.openlocfilehash: a2bf0335f8d75c7dbd1a651afdb54da8c7be2460
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731636"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="9f4a4-102">IMetaDataAssemblyImport::FindAssembliesByName (Método)</span><span class="sxs-lookup"><span data-stu-id="9f4a4-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>

<span data-ttu-id="9f4a4-103">Obtiene una matriz de ensamblados con el `szAssemblyName` parámetro especificado, utilizando las reglas estándar empleadas por el Common Language Runtime (CLR) para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f4a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f4a4-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9f4a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f4a4-105">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="9f4a4-106">de Directorio raíz en el que se va a buscar el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="9f4a4-107">Si este valor se establece en `null` , `FindAssembliesByName` solo buscará en la caché global de ensamblados el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="9f4a4-108">de Lista de subdirectorios delimitados por punto y coma (por ejemplo, "bin; bin2"), en el directorio raíz, en el que se va a buscar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="9f4a4-109">Estos directorios se sondean además de los especificados en las reglas de búsqueda predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="9f4a4-110">de Nombre del ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="9f4a4-111">El formato de esta cadena se define en la página de referencia de clase de <xref:System.Reflection.AssemblyName> .</span><span class="sxs-lookup"><span data-stu-id="9f4a4-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="9f4a4-112">de Matriz de tipo [IUnknown](/cpp/atl/iunknown) en la que se colocan los `IMetadataAssemblyImport` punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9f4a4-113">enuncia Número máximo de punteros de interfaz que se pueden colocar en `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="9f4a4-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="9f4a4-114">enuncia Número de punteros de interfaz devueltos.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="9f4a4-115">Es decir, el número de punteros de interfaz que se colocan realmente en `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="9f4a4-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f4a4-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9f4a4-116">Return Value</span></span>  
  
|<span data-ttu-id="9f4a4-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f4a4-117">HRESULT</span></span>|<span data-ttu-id="9f4a4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f4a4-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9f4a4-119">`FindAssembliesByName` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9f4a4-120">No hay ningún ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f4a4-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9f4a4-121">Remarks</span></span>  

 <span data-ttu-id="9f4a4-122">Dado un nombre de ensamblado, el `FindAssembliesByName` método busca el ensamblado siguiendo las reglas estándar para resolver las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="9f4a4-123">(Para obtener más información, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../../deployment/how-the-runtime-locates-assemblies.md)). `FindAssembliesByName` permite al llamador configurar varios aspectos del contexto de la resolución de ensamblado, como la base de la aplicación y la ruta de acceso de búsqueda privada.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-123">(For more information, see [How the Runtime Locates Assemblies](../../deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="9f4a4-124">El `FindAssembliesByName` método requiere que se inicialice el CLR en el proceso para invocar la lógica de resolución de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="9f4a4-125">Por lo tanto, debe llamar a [coinicializar](../hosting/coinitializeee-function.md) (pasando COINITEE_DEFAULT) antes de llamar a `FindAssembliesByName` y después seguir con una llamada a [couninitializecor (](../hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="9f4a4-125">Therefore, you must call [CoInitializeEE](../hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="9f4a4-126">`FindAssembliesByName` Devuelve un puntero [IMetaDataImport](imetadataimport-interface.md) al archivo que contiene el manifiesto del ensamblado para el nombre de ensamblado que se pasa.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-126">`FindAssembliesByName` returns an [IMetaDataImport](imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="9f4a4-127">Si el nombre de ensamblado especificado no se especifica completamente (por ejemplo, si no incluye una versión), es posible que se devuelvan varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="9f4a4-128">`FindAssembliesByName` suele ser utilizado por un compilador que intenta buscar un ensamblado al que se hace referencia en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="9f4a4-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f4a4-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f4a4-129">Requirements</span></span>  

 <span data-ttu-id="9f4a4-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f4a4-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f4a4-131">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9f4a4-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f4a4-132">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f4a4-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f4a4-133">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f4a4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f4a4-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f4a4-134">See also</span></span>

- [<span data-ttu-id="9f4a4-135">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="9f4a4-135">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="9f4a4-136">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f4a4-136">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
