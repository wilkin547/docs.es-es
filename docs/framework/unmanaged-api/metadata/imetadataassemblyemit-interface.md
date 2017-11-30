---
title: IMetaDataAssemblyEmit (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit
helpviewer_keywords: IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af7a5fd5a564aa7366924f47b0c526aff7153521
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="ac057-102">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac057-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="ac057-103">Proporciona métodos que admiten el modelo autodescriptivo usado por Common Language Runtime para resolver y consumir recursos.</span><span class="sxs-lookup"><span data-stu-id="ac057-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac057-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ac057-104">Methods</span></span>  
  
|<span data-ttu-id="ac057-105">Método</span><span class="sxs-lookup"><span data-stu-id="ac057-105">Method</span></span>|<span data-ttu-id="ac057-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac057-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac057-107">DefineAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="ac057-108">Crea una estructura de datos de ensamblado que contiene los metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="ac057-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="ac057-109">DefineAssemblyRef (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="ac057-110">Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="ac057-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="ac057-111">DefineExportedType (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="ac057-112">Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="ac057-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="ac057-113">DefineFile (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="ac057-114">Crea una estructura de metadatos `File` que contiene los metadatos para el ensamblado al que se refiere este ensamblado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="ac057-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="ac057-115">DefineManifestResource (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="ac057-116">Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="ac057-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="ac057-117">SetAssemblyProps (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="ac057-118">Modifica la estructura de metadatos `Assembly` especificada.</span><span class="sxs-lookup"><span data-stu-id="ac057-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="ac057-119">SetAssemblyRefProps (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="ac057-120">Modifica la estructura de metadatos `AssemblyRef` especificada.</span><span class="sxs-lookup"><span data-stu-id="ac057-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="ac057-121">SetExportedTypeProps (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="ac057-122">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="ac057-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="ac057-123">SetFileProps (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="ac057-124">Modifica la estructura de metadatos `File` especificada.</span><span class="sxs-lookup"><span data-stu-id="ac057-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="ac057-125">SetManifestResourceProps (método)</span><span class="sxs-lookup"><span data-stu-id="ac057-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="ac057-126">Modifica la estructura de metadatos `ManifestResource` especificada.</span><span class="sxs-lookup"><span data-stu-id="ac057-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac057-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac057-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac057-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac057-128">Requirements</span></span>  
 <span data-ttu-id="ac057-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac057-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac057-130">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ac057-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac057-131">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac057-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac057-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac057-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac057-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac057-133">See Also</span></span>  
 [<span data-ttu-id="ac057-134">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="ac057-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="ac057-135">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac057-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
