---
title: IMetaDataAssemblyImport (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport
helpviewer_keywords: IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ef5b913dc9b1391c63cb123e1f922ca61da6a5bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="1d6da-102">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d6da-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="1d6da-103">Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.</span><span class="sxs-lookup"><span data-stu-id="1d6da-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d6da-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1d6da-104">Methods</span></span>  
  
|<span data-ttu-id="1d6da-105">Método</span><span class="sxs-lookup"><span data-stu-id="1d6da-105">Method</span></span>|<span data-ttu-id="1d6da-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d6da-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d6da-107">CloseEnum (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="1d6da-108">Libera el identificador para el enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="1d6da-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="1d6da-109">EnumAssemblyRefs (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="1d6da-110">Obtiene un puntero de interfaz a un enumerador que contiene el `mdAssemblyRef` símbolos (tokens) de los ensamblados al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1d6da-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1d6da-111">EnumExportedTypes (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="1d6da-112">Obtiene un puntero de interfaz a un enumerador que contiene el `mdExportedType` símbolos (tokens) de los tipos COM al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1d6da-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1d6da-113">EnumFiles (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="1d6da-114">Obtiene un puntero de interfaz a un enumerador que contiene el `mdFile` símbolos (tokens) de los archivos al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1d6da-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1d6da-115">EnumManifestResources (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="1d6da-116">Obtiene un puntero de interfaz a un enumerador que contiene el `mdManifestResource` símbolos (tokens) de los recursos al que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1d6da-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1d6da-117">FindAssembliesByName (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="1d6da-118">Obtiene una matriz de `mdAssemblyRef` tokens para los ensamblados con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="1d6da-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="1d6da-119">FindExportedTypeByName (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="1d6da-120">Obtiene un `mdExportedType` token para el tipo COM con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="1d6da-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="1d6da-121">FindManifestResourceByName (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="1d6da-122">Obtiene un `mdManifestResource` token para el recurso con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="1d6da-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="1d6da-123">GetAssemblyFromScope (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="1d6da-124">Obtiene el token para el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1d6da-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="1d6da-125">GetAssemblyProps (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="1d6da-126">Obtiene los valores de propiedades del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="1d6da-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="1d6da-127">GetAssemblyRefProps (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="1d6da-128">Obtiene los valores de propiedad del elemento especificado `mdAssemblyRef` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="1d6da-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="1d6da-129">GetExportedTypeProps (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="1d6da-130">Obtiene los valores de propiedad del tipo COM especificado.</span><span class="sxs-lookup"><span data-stu-id="1d6da-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="1d6da-131">GetFileProps (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="1d6da-132">Obtiene los valores de propiedades del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="1d6da-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="1d6da-133">GetManifestResourceProps (método)</span><span class="sxs-lookup"><span data-stu-id="1d6da-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="1d6da-134">Obtiene los valores de propiedad de recurso del manifiesto especificado.</span><span class="sxs-lookup"><span data-stu-id="1d6da-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d6da-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d6da-135">Requirements</span></span>  
 <span data-ttu-id="1d6da-136">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d6da-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d6da-137">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1d6da-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d6da-138">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d6da-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d6da-139">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d6da-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d6da-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d6da-140">See Also</span></span>  
 [<span data-ttu-id="1d6da-141">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="1d6da-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="1d6da-142">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d6da-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
