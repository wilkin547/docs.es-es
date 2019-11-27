---
title: IMetaDataAssemblyImport (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: 289e26868ff2eb9e1d97cf084e9a888815062ea4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436310"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="1f46c-102">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f46c-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="1f46c-103">Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.</span><span class="sxs-lookup"><span data-stu-id="1f46c-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f46c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1f46c-104">Methods</span></span>  
  
|<span data-ttu-id="1f46c-105">Método</span><span class="sxs-lookup"><span data-stu-id="1f46c-105">Method</span></span>|<span data-ttu-id="1f46c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f46c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f46c-107">CloseEnum (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="1f46c-108">Libera el identificador del enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="1f46c-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="1f46c-109">EnumAssemblyRefs (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="1f46c-110">Obtiene un puntero de interfaz a un enumerador que contiene los tokens `mdAssemblyRef` de los ensamblados a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1f46c-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1f46c-111">EnumExportedTypes (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="1f46c-112">Obtiene un puntero de interfaz a un enumerador que contiene los tokens `mdExportedType` de los tipos COM a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1f46c-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1f46c-113">EnumFiles (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="1f46c-114">Obtiene un puntero de interfaz a un enumerador que contiene los tokens `mdFile` de los archivos a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1f46c-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1f46c-115">EnumManifestResources (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="1f46c-116">Obtiene un puntero de interfaz a un enumerador que contiene los tokens `mdManifestResource` de los recursos a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1f46c-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1f46c-117">FindAssembliesByName (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="1f46c-118">Obtiene una matriz de `mdAssemblyRef` tokens para los ensamblados con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="1f46c-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="1f46c-119">FindExportedTypeByName (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="1f46c-120">Obtiene un token de `mdExportedType` para el tipo COM con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="1f46c-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="1f46c-121">FindManifestResourceByName (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="1f46c-122">Obtiene un token de `mdManifestResource` para el recurso con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="1f46c-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="1f46c-123">GetAssemblyFromScope (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="1f46c-124">Obtiene el token para el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1f46c-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1f46c-125">GetAssemblyProps (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="1f46c-126">Obtiene los valores de propiedad del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="1f46c-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="1f46c-127">GetAssemblyRefProps (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="1f46c-128">Obtiene los valores de propiedad del token de `mdAssemblyRef` especificado.</span><span class="sxs-lookup"><span data-stu-id="1f46c-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="1f46c-129">GetExportedTypeProps (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="1f46c-130">Obtiene los valores de propiedad del tipo COM especificado.</span><span class="sxs-lookup"><span data-stu-id="1f46c-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="1f46c-131">GetFileProps (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="1f46c-132">Obtiene los valores de propiedad del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="1f46c-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="1f46c-133">GetManifestResourceProps (método)</span><span class="sxs-lookup"><span data-stu-id="1f46c-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="1f46c-134">Obtiene los valores de propiedad del recurso de manifiesto especificado.</span><span class="sxs-lookup"><span data-stu-id="1f46c-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f46c-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f46c-135">Requirements</span></span>  
 <span data-ttu-id="1f46c-136">**Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f46c-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f46c-137">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1f46c-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1f46c-138">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1f46c-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1f46c-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f46c-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f46c-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f46c-140">See also</span></span>

- [<span data-ttu-id="1f46c-141">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="1f46c-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="1f46c-142">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f46c-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
