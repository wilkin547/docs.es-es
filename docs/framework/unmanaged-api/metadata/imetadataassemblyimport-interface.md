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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112637"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="88a45-102">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88a45-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="88a45-103">Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.</span><span class="sxs-lookup"><span data-stu-id="88a45-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88a45-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="88a45-104">Methods</span></span>  
  
|<span data-ttu-id="88a45-105">Método</span><span class="sxs-lookup"><span data-stu-id="88a45-105">Method</span></span>|<span data-ttu-id="88a45-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="88a45-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88a45-107">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="88a45-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="88a45-108">Libera el identificador del enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="88a45-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="88a45-109">Método EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="88a45-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="88a45-110">Obtiene un puntero de interfaz a un enumerador que contiene el `mdAssemblyRef` tokens de los ensamblados que se hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="88a45-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="88a45-111">Método EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="88a45-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="88a45-112">Obtiene un puntero de interfaz a un enumerador que contiene el `mdExportedType` tokens de los tipos COM al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="88a45-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="88a45-113">Método EnumFiles</span><span class="sxs-lookup"><span data-stu-id="88a45-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="88a45-114">Obtiene un puntero de interfaz a un enumerador que contiene el `mdFile` tokens de los archivos al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="88a45-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="88a45-115">Método EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="88a45-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="88a45-116">Obtiene un puntero de interfaz a un enumerador que contiene el `mdManifestResource` tokens de los recursos al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="88a45-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="88a45-117">Método FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="88a45-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="88a45-118">Obtiene una matriz de `mdAssemblyRef` tokens para los ensamblados con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="88a45-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="88a45-119">Método FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="88a45-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="88a45-120">Obtiene un `mdExportedType` token para el tipo COM con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="88a45-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="88a45-121">Método FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="88a45-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="88a45-122">Obtiene un `mdManifestResource` token para el recurso con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="88a45-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="88a45-123">Método GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="88a45-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="88a45-124">Obtiene el token para el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="88a45-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="88a45-125">Método GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="88a45-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="88a45-126">Obtiene los valores de propiedad del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="88a45-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="88a45-127">Método GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="88a45-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="88a45-128">Obtiene los valores de propiedad del elemento especificado `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="88a45-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="88a45-129">Método GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="88a45-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="88a45-130">Obtiene los valores de propiedad del tipo COM especificado.</span><span class="sxs-lookup"><span data-stu-id="88a45-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="88a45-131">Método GetFileProps</span><span class="sxs-lookup"><span data-stu-id="88a45-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="88a45-132">Obtiene los valores de propiedad del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="88a45-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="88a45-133">Método GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="88a45-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="88a45-134">Obtiene los valores de propiedad del recurso del manifiesto especificado.</span><span class="sxs-lookup"><span data-stu-id="88a45-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88a45-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88a45-135">Requirements</span></span>  
 <span data-ttu-id="88a45-136">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88a45-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88a45-137">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="88a45-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88a45-138">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88a45-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="88a45-139">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="88a45-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="88a45-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="88a45-140">See also</span></span>

- [<span data-ttu-id="88a45-141">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="88a45-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="88a45-142">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88a45-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
