---
title: IMetaDataDispenser (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser
helpviewer_keywords: IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5a0464f2fb7b81d98fcbb4b04bc465cf57b1b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="5a7c5-102">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a7c5-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="5a7c5-103">Proporciona métodos para crear un nuevo ámbito de metadatos, o abrir uno existente.</span><span class="sxs-lookup"><span data-stu-id="5a7c5-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a7c5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5a7c5-104">Methods</span></span>  
  
|<span data-ttu-id="5a7c5-105">Método</span><span class="sxs-lookup"><span data-stu-id="5a7c5-105">Method</span></span>|<span data-ttu-id="5a7c5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a7c5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a7c5-107">DefineScope (método)</span><span class="sxs-lookup"><span data-stu-id="5a7c5-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="5a7c5-108">Crea una nueva área de memoria donde puede crear nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="5a7c5-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="5a7c5-109">OpenScope (método)</span><span class="sxs-lookup"><span data-stu-id="5a7c5-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="5a7c5-110">Abre un archivo existente, en el disco y asigna sus metadatos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="5a7c5-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="5a7c5-111">OpenScopeOnMemory (método)</span><span class="sxs-lookup"><span data-stu-id="5a7c5-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="5a7c5-112">Abre un área de memoria que contiene los metadatos existentes.</span><span class="sxs-lookup"><span data-stu-id="5a7c5-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="5a7c5-113">Es decir, este método abre un área especificada de memoria en el que los datos existentes se tratan como metadatos.</span><span class="sxs-lookup"><span data-stu-id="5a7c5-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a7c5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a7c5-114">Requirements</span></span>  
 <span data-ttu-id="5a7c5-115">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a7c5-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a7c5-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a7c5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a7c5-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a7c5-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a7c5-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a7c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7c5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a7c5-119">See Also</span></span>  
 [<span data-ttu-id="5a7c5-120">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a7c5-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="5a7c5-121">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="5a7c5-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
