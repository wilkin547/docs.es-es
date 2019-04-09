---
title: IMetaDataAssemblyEmit (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a66ef090a205019493e099919739867e3936873
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081808"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="927ab-102">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="927ab-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="927ab-103">Proporciona métodos que admiten el modelo autodescriptivo usado por Common Language Runtime para resolver y consumir recursos.</span><span class="sxs-lookup"><span data-stu-id="927ab-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="927ab-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="927ab-104">Methods</span></span>  
  
|<span data-ttu-id="927ab-105">Método</span><span class="sxs-lookup"><span data-stu-id="927ab-105">Method</span></span>|<span data-ttu-id="927ab-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="927ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="927ab-107">Método DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="927ab-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="927ab-108">Crea una estructura de datos de ensamblado que contiene los metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="927ab-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="927ab-109">Método DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="927ab-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="927ab-110">Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="927ab-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="927ab-111">Método DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="927ab-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="927ab-112">Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="927ab-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="927ab-113">Método DefineFile</span><span class="sxs-lookup"><span data-stu-id="927ab-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="927ab-114">Crea una estructura de metadatos `File` que contiene los metadatos para el ensamblado al que se refiere este ensamblado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="927ab-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="927ab-115">Método DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="927ab-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="927ab-116">Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="927ab-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="927ab-117">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="927ab-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="927ab-118">Modifica la estructura de metadatos `Assembly` especificada.</span><span class="sxs-lookup"><span data-stu-id="927ab-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="927ab-119">Método SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="927ab-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="927ab-120">Modifica la estructura de metadatos `AssemblyRef` especificada.</span><span class="sxs-lookup"><span data-stu-id="927ab-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="927ab-121">Método SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="927ab-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="927ab-122">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="927ab-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="927ab-123">Método SetFileProps</span><span class="sxs-lookup"><span data-stu-id="927ab-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="927ab-124">Modifica la estructura de metadatos `File` especificada.</span><span class="sxs-lookup"><span data-stu-id="927ab-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="927ab-125">Método SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="927ab-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="927ab-126">Modifica la estructura de metadatos `ManifestResource` especificada.</span><span class="sxs-lookup"><span data-stu-id="927ab-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="927ab-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="927ab-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="927ab-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="927ab-128">Requirements</span></span>  
 <span data-ttu-id="927ab-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="927ab-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="927ab-130">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="927ab-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="927ab-131">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="927ab-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="927ab-132">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="927ab-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="927ab-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="927ab-133">See also</span></span>

- [<span data-ttu-id="927ab-134">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="927ab-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="927ab-135">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="927ab-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
