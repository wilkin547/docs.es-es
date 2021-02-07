---
description: 'Más información acerca de: interfaz IMetaDataAssemblyImport'
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
ms.openlocfilehash: bb9c5163e4f5b68700e5a3836fa55edbbebac01c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753645"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="41456-103">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="41456-103">IMetaDataAssemblyImport Interface</span></span>

<span data-ttu-id="41456-104">Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.</span><span class="sxs-lookup"><span data-stu-id="41456-104">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41456-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="41456-105">Methods</span></span>  
  
|<span data-ttu-id="41456-106">Método</span><span class="sxs-lookup"><span data-stu-id="41456-106">Method</span></span>|<span data-ttu-id="41456-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="41456-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41456-108">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="41456-108">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="41456-109">Libera el identificador del enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="41456-109">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="41456-110">Método EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="41456-110">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="41456-111">Obtiene un puntero de interfaz a un enumerador que contiene los `mdAssemblyRef` tokens de los ensamblados a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="41456-111">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41456-112">Método EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="41456-112">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="41456-113">Obtiene un puntero de interfaz a un enumerador que contiene los `mdExportedType` tokens de los tipos com a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="41456-113">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41456-114">Método EnumFiles</span><span class="sxs-lookup"><span data-stu-id="41456-114">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="41456-115">Obtiene un puntero de interfaz a un enumerador que contiene los `mdFile` tokens de los archivos a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="41456-115">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41456-116">Método EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="41456-116">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="41456-117">Obtiene un puntero de interfaz a un enumerador que contiene los `mdManifestResource` tokens de los recursos a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="41456-117">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41456-118">Método FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="41456-118">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="41456-119">Obtiene una matriz de `mdAssemblyRef` tokens para los ensamblados con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="41456-119">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="41456-120">Método FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="41456-120">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="41456-121">Obtiene un `mdExportedType` token para el tipo com con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="41456-121">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="41456-122">Método FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="41456-122">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="41456-123">Obtiene un `mdManifestResource` token para el recurso con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="41456-123">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="41456-124">Método GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="41456-124">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="41456-125">Obtiene el token para el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="41456-125">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41456-126">Método GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="41456-126">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="41456-127">Obtiene los valores de propiedad del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="41456-127">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="41456-128">Método GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="41456-128">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="41456-129">Obtiene los valores de propiedad del `mdAssemblyRef` token especificado.</span><span class="sxs-lookup"><span data-stu-id="41456-129">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="41456-130">Método GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="41456-130">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="41456-131">Obtiene los valores de propiedad del tipo COM especificado.</span><span class="sxs-lookup"><span data-stu-id="41456-131">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="41456-132">Método GetFileProps</span><span class="sxs-lookup"><span data-stu-id="41456-132">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="41456-133">Obtiene los valores de propiedad del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="41456-133">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="41456-134">Método GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="41456-134">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="41456-135">Obtiene los valores de propiedad del recurso de manifiesto especificado.</span><span class="sxs-lookup"><span data-stu-id="41456-135">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41456-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41456-136">Requirements</span></span>  

 <span data-ttu-id="41456-137">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41456-137">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41456-138">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="41456-138">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41456-139">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41456-139">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41456-140">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41456-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41456-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="41456-141">See also</span></span>

- [<span data-ttu-id="41456-142">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="41456-142">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="41456-143">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="41456-143">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
