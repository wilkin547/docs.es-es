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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 373ff0470e2403f91534df0c0ffe4039dbb0f832
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112637"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="b9f38-102">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9f38-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="b9f38-103">Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.</span><span class="sxs-lookup"><span data-stu-id="b9f38-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9f38-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b9f38-104">Methods</span></span>  
  
|<span data-ttu-id="b9f38-105">Método</span><span class="sxs-lookup"><span data-stu-id="b9f38-105">Method</span></span>|<span data-ttu-id="b9f38-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9f38-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9f38-107">CloseEnum (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="b9f38-108">Libera el identificador del enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="b9f38-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="b9f38-109">EnumAssemblyRefs (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="b9f38-110">Obtiene un puntero de interfaz a un enumerador que contiene el `mdAssemblyRef` tokens de los ensamblados que se hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b9f38-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="b9f38-111">EnumExportedTypes (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="b9f38-112">Obtiene un puntero de interfaz a un enumerador que contiene el `mdExportedType` tokens de los tipos COM al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b9f38-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="b9f38-113">EnumFiles (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="b9f38-114">Obtiene un puntero de interfaz a un enumerador que contiene el `mdFile` tokens de los archivos al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b9f38-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="b9f38-115">EnumManifestResources (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="b9f38-116">Obtiene un puntero de interfaz a un enumerador que contiene el `mdManifestResource` tokens de los recursos al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b9f38-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="b9f38-117">FindAssembliesByName (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="b9f38-118">Obtiene una matriz de `mdAssemblyRef` tokens para los ensamblados con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="b9f38-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="b9f38-119">FindExportedTypeByName (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="b9f38-120">Obtiene un `mdExportedType` token para el tipo COM con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="b9f38-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="b9f38-121">FindManifestResourceByName (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="b9f38-122">Obtiene un `mdManifestResource` token para el recurso con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="b9f38-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="b9f38-123">GetAssemblyFromScope (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="b9f38-124">Obtiene el token para el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b9f38-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="b9f38-125">GetAssemblyProps (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="b9f38-126">Obtiene los valores de propiedad del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="b9f38-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="b9f38-127">GetAssemblyRefProps (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="b9f38-128">Obtiene los valores de propiedad del elemento especificado `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="b9f38-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="b9f38-129">GetExportedTypeProps (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="b9f38-130">Obtiene los valores de propiedad del tipo COM especificado.</span><span class="sxs-lookup"><span data-stu-id="b9f38-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="b9f38-131">GetFileProps (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="b9f38-132">Obtiene los valores de propiedad del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="b9f38-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="b9f38-133">GetManifestResourceProps (método)</span><span class="sxs-lookup"><span data-stu-id="b9f38-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="b9f38-134">Obtiene los valores de propiedad del recurso del manifiesto especificado.</span><span class="sxs-lookup"><span data-stu-id="b9f38-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9f38-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9f38-135">Requirements</span></span>  
 <span data-ttu-id="b9f38-136">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f38-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f38-137">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b9f38-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9f38-138">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9f38-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9f38-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f38-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f38-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9f38-140">See also</span></span>

- [<span data-ttu-id="b9f38-141">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="b9f38-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b9f38-142">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9f38-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
