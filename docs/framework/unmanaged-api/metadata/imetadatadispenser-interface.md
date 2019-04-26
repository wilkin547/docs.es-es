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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904766"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="ef298-102">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef298-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="ef298-103">Proporciona métodos para crear un nuevo ámbito de metadatos, o abrir uno existente.</span><span class="sxs-lookup"><span data-stu-id="ef298-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ef298-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ef298-104">Methods</span></span>  
  
|<span data-ttu-id="ef298-105">Método</span><span class="sxs-lookup"><span data-stu-id="ef298-105">Method</span></span>|<span data-ttu-id="ef298-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef298-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef298-107">DefineScope (método)</span><span class="sxs-lookup"><span data-stu-id="ef298-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="ef298-108">Crea una nueva área de memoria donde puede crear nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="ef298-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="ef298-109">OpenScope (método)</span><span class="sxs-lookup"><span data-stu-id="ef298-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="ef298-110">Se abre un archivo existente, en el disco y asigna sus metadatos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="ef298-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="ef298-111">OpenScopeOnMemory (método)</span><span class="sxs-lookup"><span data-stu-id="ef298-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="ef298-112">Se abre un área de memoria que contiene los metadatos existentes.</span><span class="sxs-lookup"><span data-stu-id="ef298-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="ef298-113">Es decir, este método abre un área especificada de memoria en el que los datos existentes se tratan como metadatos.</span><span class="sxs-lookup"><span data-stu-id="ef298-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef298-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef298-114">Requirements</span></span>  
 <span data-ttu-id="ef298-115">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef298-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef298-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ef298-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef298-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef298-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef298-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef298-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef298-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef298-119">See also</span></span>

- [<span data-ttu-id="ef298-120">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef298-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="ef298-121">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="ef298-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
