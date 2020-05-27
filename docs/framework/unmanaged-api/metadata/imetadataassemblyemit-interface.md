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
ms.openlocfilehash: 807e1ee831a43a4ef1e7b0a269ee38131f24081e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008126"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="f434c-102">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f434c-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="f434c-103">Proporciona métodos que admiten el modelo autodescriptivo usado por Common Language Runtime para resolver y consumir recursos.</span><span class="sxs-lookup"><span data-stu-id="f434c-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f434c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f434c-104">Methods</span></span>  
  
|<span data-ttu-id="f434c-105">Método</span><span class="sxs-lookup"><span data-stu-id="f434c-105">Method</span></span>|<span data-ttu-id="f434c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f434c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f434c-107">Método DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="f434c-107">DefineAssembly Method</span></span>](imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="f434c-108">Crea una estructura de datos de ensamblado que contiene los metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="f434c-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f434c-109">Método DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="f434c-109">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="f434c-110">Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="f434c-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f434c-111">Método DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="f434c-111">DefineExportedType Method</span></span>](imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="f434c-112">Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="f434c-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f434c-113">Método DefineFile</span><span class="sxs-lookup"><span data-stu-id="f434c-113">DefineFile Method</span></span>](imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="f434c-114">Crea una estructura de metadatos `File` que contiene los metadatos para el ensamblado al que se refiere este ensamblado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="f434c-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f434c-115">Método DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="f434c-115">DefineManifestResource Method</span></span>](imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="f434c-116">Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="f434c-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f434c-117">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="f434c-117">SetAssemblyProps Method</span></span>](imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="f434c-118">Modifica la estructura de metadatos `Assembly` especificada.</span><span class="sxs-lookup"><span data-stu-id="f434c-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="f434c-119">Método SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="f434c-119">SetAssemblyRefProps Method</span></span>](imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="f434c-120">Modifica la estructura de metadatos `AssemblyRef` especificada.</span><span class="sxs-lookup"><span data-stu-id="f434c-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="f434c-121">Método SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="f434c-121">SetExportedTypeProps Method</span></span>](imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="f434c-122">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="f434c-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="f434c-123">Método SetFileProps</span><span class="sxs-lookup"><span data-stu-id="f434c-123">SetFileProps Method</span></span>](imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="f434c-124">Modifica la estructura de metadatos `File` especificada.</span><span class="sxs-lookup"><span data-stu-id="f434c-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="f434c-125">Método SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="f434c-125">SetManifestResourceProps Method</span></span>](imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="f434c-126">Modifica la estructura de metadatos `ManifestResource` especificada.</span><span class="sxs-lookup"><span data-stu-id="f434c-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f434c-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f434c-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f434c-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f434c-128">Requirements</span></span>  
 <span data-ttu-id="f434c-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f434c-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f434c-130">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f434c-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f434c-131">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f434c-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f434c-132">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f434c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f434c-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f434c-133">See also</span></span>

- [<span data-ttu-id="f434c-134">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="f434c-134">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="f434c-135">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f434c-135">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
