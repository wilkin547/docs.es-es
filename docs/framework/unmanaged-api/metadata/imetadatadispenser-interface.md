---
title: IMetaDataDispenser (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dda284fc86f0a82472c59d6bab08fd4a87364723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225981"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="1f2b9-102">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f2b9-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="1f2b9-103">Proporciona métodos para crear un nuevo ámbito de metadatos, o abrir uno existente.</span><span class="sxs-lookup"><span data-stu-id="1f2b9-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f2b9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1f2b9-104">Methods</span></span>  
  
|<span data-ttu-id="1f2b9-105">Método</span><span class="sxs-lookup"><span data-stu-id="1f2b9-105">Method</span></span>|<span data-ttu-id="1f2b9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f2b9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f2b9-107">Método DefineScope</span><span class="sxs-lookup"><span data-stu-id="1f2b9-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="1f2b9-108">Crea una nueva área de memoria donde puede crear nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="1f2b9-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="1f2b9-109">Método OpenScope</span><span class="sxs-lookup"><span data-stu-id="1f2b9-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="1f2b9-110">Se abre un archivo existente, en el disco y asigna sus metadatos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="1f2b9-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="1f2b9-111">Método OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="1f2b9-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="1f2b9-112">Se abre un área de memoria que contiene los metadatos existentes.</span><span class="sxs-lookup"><span data-stu-id="1f2b9-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="1f2b9-113">Es decir, este método abre un área especificada de memoria en el que los datos existentes se tratan como metadatos.</span><span class="sxs-lookup"><span data-stu-id="1f2b9-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f2b9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f2b9-114">Requirements</span></span>  
 <span data-ttu-id="1f2b9-115">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f2b9-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f2b9-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="1f2b9-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1f2b9-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1f2b9-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1f2b9-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1f2b9-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1f2b9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f2b9-119">See also</span></span>

- [<span data-ttu-id="1f2b9-120">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f2b9-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="1f2b9-121">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="1f2b9-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
