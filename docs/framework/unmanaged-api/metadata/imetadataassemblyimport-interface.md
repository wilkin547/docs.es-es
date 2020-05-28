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
ms.openlocfilehash: 2a67f50fa1042e8d3957a9a0394507f260a328c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009020"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="bd2d3-102">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd2d3-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="bd2d3-103">Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd2d3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bd2d3-104">Methods</span></span>  
  
|<span data-ttu-id="bd2d3-105">Método</span><span class="sxs-lookup"><span data-stu-id="bd2d3-105">Method</span></span>|<span data-ttu-id="bd2d3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd2d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd2d3-107">CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="bd2d3-107">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="bd2d3-108">Libera el identificador del enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="bd2d3-109">Método EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="bd2d3-109">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="bd2d3-110">Obtiene un puntero de interfaz a un enumerador que contiene los `mdAssemblyRef` tokens de los ensamblados a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="bd2d3-111">Método EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="bd2d3-111">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="bd2d3-112">Obtiene un puntero de interfaz a un enumerador que contiene los `mdExportedType` tokens de los tipos com a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="bd2d3-113">Método EnumFiles</span><span class="sxs-lookup"><span data-stu-id="bd2d3-113">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="bd2d3-114">Obtiene un puntero de interfaz a un enumerador que contiene los `mdFile` tokens de los archivos a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="bd2d3-115">Método EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="bd2d3-115">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="bd2d3-116">Obtiene un puntero de interfaz a un enumerador que contiene los `mdManifestResource` tokens de los recursos a los que hace referencia el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="bd2d3-117">Método FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="bd2d3-117">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="bd2d3-118">Obtiene una matriz de `mdAssemblyRef` tokens para los ensamblados con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="bd2d3-119">Método FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="bd2d3-119">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="bd2d3-120">Obtiene un `mdExportedType` token para el tipo com con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="bd2d3-121">Método FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="bd2d3-121">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="bd2d3-122">Obtiene un `mdManifestResource` token para el recurso con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="bd2d3-123">Método GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="bd2d3-123">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="bd2d3-124">Obtiene el token para el ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="bd2d3-125">Método GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="bd2d3-125">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="bd2d3-126">Obtiene los valores de propiedad del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="bd2d3-127">Método GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="bd2d3-127">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="bd2d3-128">Obtiene los valores de propiedad del `mdAssemblyRef` token especificado.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="bd2d3-129">Método GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="bd2d3-129">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="bd2d3-130">Obtiene los valores de propiedad del tipo COM especificado.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="bd2d3-131">Método GetFileProps</span><span class="sxs-lookup"><span data-stu-id="bd2d3-131">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="bd2d3-132">Obtiene los valores de propiedad del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="bd2d3-133">Método GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="bd2d3-133">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="bd2d3-134">Obtiene los valores de propiedad del recurso de manifiesto especificado.</span><span class="sxs-lookup"><span data-stu-id="bd2d3-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd2d3-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd2d3-135">Requirements</span></span>  
 <span data-ttu-id="bd2d3-136">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd2d3-136">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd2d3-137">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bd2d3-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd2d3-138">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bd2d3-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd2d3-139">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd2d3-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd2d3-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd2d3-140">See also</span></span>

- [<span data-ttu-id="bd2d3-141">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="bd2d3-141">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="bd2d3-142">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd2d3-142">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
