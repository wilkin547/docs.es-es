---
description: 'Más información acerca de: IMetaDataAssemblyEmit (interfaz)'
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
ms.openlocfilehash: bcfca4eedc14f2292c40874d86c4984b4c1948f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678216"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="b69b8-103">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b69b8-103">IMetaDataAssemblyEmit Interface</span></span>

<span data-ttu-id="b69b8-104">Proporciona métodos que admiten el modelo autodescriptivo usado por Common Language Runtime para resolver y consumir recursos.</span><span class="sxs-lookup"><span data-stu-id="b69b8-104">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b69b8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b69b8-105">Methods</span></span>  
  
|<span data-ttu-id="b69b8-106">Método</span><span class="sxs-lookup"><span data-stu-id="b69b8-106">Method</span></span>|<span data-ttu-id="b69b8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b69b8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b69b8-108">Método DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="b69b8-108">DefineAssembly Method</span></span>](imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="b69b8-109">Crea una estructura de datos de ensamblado que contiene los metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="b69b8-109">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b69b8-110">Método DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="b69b8-110">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="b69b8-111">Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="b69b8-111">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b69b8-112">Método DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="b69b8-112">DefineExportedType Method</span></span>](imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="b69b8-113">Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="b69b8-113">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b69b8-114">Método DefineFile</span><span class="sxs-lookup"><span data-stu-id="b69b8-114">DefineFile Method</span></span>](imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="b69b8-115">Crea una estructura de metadatos `File` que contiene los metadatos para el ensamblado al que se refiere este ensamblado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="b69b8-115">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b69b8-116">Método DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="b69b8-116">DefineManifestResource Method</span></span>](imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="b69b8-117">Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="b69b8-117">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b69b8-118">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="b69b8-118">SetAssemblyProps Method</span></span>](imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="b69b8-119">Modifica la estructura de metadatos `Assembly` especificada.</span><span class="sxs-lookup"><span data-stu-id="b69b8-119">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="b69b8-120">Método SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="b69b8-120">SetAssemblyRefProps Method</span></span>](imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="b69b8-121">Modifica la estructura de metadatos `AssemblyRef` especificada.</span><span class="sxs-lookup"><span data-stu-id="b69b8-121">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="b69b8-122">Método SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="b69b8-122">SetExportedTypeProps Method</span></span>](imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="b69b8-123">Modifica la estructura de metadatos `ExportedType` especificada.</span><span class="sxs-lookup"><span data-stu-id="b69b8-123">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="b69b8-124">Método SetFileProps</span><span class="sxs-lookup"><span data-stu-id="b69b8-124">SetFileProps Method</span></span>](imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="b69b8-125">Modifica la estructura de metadatos `File` especificada.</span><span class="sxs-lookup"><span data-stu-id="b69b8-125">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="b69b8-126">Método SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="b69b8-126">SetManifestResourceProps Method</span></span>](imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="b69b8-127">Modifica la estructura de metadatos `ManifestResource` especificada.</span><span class="sxs-lookup"><span data-stu-id="b69b8-127">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b69b8-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b69b8-128">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b69b8-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b69b8-129">Requirements</span></span>  

 <span data-ttu-id="b69b8-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b69b8-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b69b8-131">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b69b8-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b69b8-132">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b69b8-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b69b8-133">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b69b8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b69b8-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b69b8-134">See also</span></span>

- [<span data-ttu-id="b69b8-135">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="b69b8-135">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="b69b8-136">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b69b8-136">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
