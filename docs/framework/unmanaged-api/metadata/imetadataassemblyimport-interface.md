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
ms.openlocfilehash: c556fe247754b363ece0c5dc60750068276ddcc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714762"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="8912b-102">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8912b-102">IMetaDataAssemblyImport Interface</span></span>

<span data-ttu-id="8912b-103">Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.</span><span class="sxs-lookup"><span data-stu-id="8912b-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8912b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8912b-104">Methods</span></span>  
  
|<span data-ttu-id="8912b-105">Método</span><span class="sxs-lookup"><span data-stu-id="8912b-105">Method</span></span>|<span data-ttu-id="8912b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8912b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8912b-107">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="8912b-107">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="8912b-108">Libera el identificador del enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="8912b-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="8912b-109">Método EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="8912b-109">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="8912b-110">Obtiene un puntero de interfaz a un enumerador que contiene los `mdAssemblyRef` tokens de los ensamblados a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="8912b-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="8912b-111">Método EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="8912b-111">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="8912b-112">Obtiene un puntero de interfaz a un enumerador que contiene los `mdExportedType` tokens de los tipos com a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="8912b-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="8912b-113">Método EnumFiles</span><span class="sxs-lookup"><span data-stu-id="8912b-113">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="8912b-114">Obtiene un puntero de interfaz a un enumerador que contiene los `mdFile` tokens de los archivos a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="8912b-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="8912b-115">Método EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="8912b-115">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="8912b-116">Obtiene un puntero de interfaz a un enumerador que contiene los `mdManifestResource` tokens de los recursos a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="8912b-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="8912b-117">Método FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="8912b-117">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="8912b-118">Obtiene una matriz de `mdAssemblyRef` tokens para los ensamblados con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="8912b-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="8912b-119">Método FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="8912b-119">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="8912b-120">Obtiene un `mdExportedType` token para el tipo com con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="8912b-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="8912b-121">Método FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="8912b-121">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="8912b-122">Obtiene un `mdManifestResource` token para el recurso con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="8912b-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="8912b-123">Método GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="8912b-123">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="8912b-124">Obtiene el token para el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="8912b-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="8912b-125">Método GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="8912b-125">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="8912b-126">Obtiene los valores de propiedad del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="8912b-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="8912b-127">Método GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="8912b-127">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="8912b-128">Obtiene los valores de propiedad del `mdAssemblyRef` token especificado.</span><span class="sxs-lookup"><span data-stu-id="8912b-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="8912b-129">Método GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="8912b-129">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="8912b-130">Obtiene los valores de propiedad del tipo COM especificado.</span><span class="sxs-lookup"><span data-stu-id="8912b-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="8912b-131">Método GetFileProps</span><span class="sxs-lookup"><span data-stu-id="8912b-131">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="8912b-132">Obtiene los valores de propiedad del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="8912b-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="8912b-133">Método GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="8912b-133">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="8912b-134">Obtiene los valores de propiedad del recurso de manifiesto especificado.</span><span class="sxs-lookup"><span data-stu-id="8912b-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8912b-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8912b-135">Requirements</span></span>  

 <span data-ttu-id="8912b-136">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8912b-136">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8912b-137">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8912b-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8912b-138">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8912b-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8912b-139">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8912b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8912b-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8912b-140">See also</span></span>

- [<span data-ttu-id="8912b-141">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="8912b-141">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="8912b-142">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8912b-142">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
