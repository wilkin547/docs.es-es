---
description: 'Más información acerca de: IMetaDataDispenser (interfaz)'
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
ms.openlocfilehash: 5ba37fc05a4e1897b100967d32b268f91a0e4402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721013"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="0f5c2-103">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f5c2-103">IMetaDataDispenser Interface</span></span>

<span data-ttu-id="0f5c2-104">Proporciona métodos para crear un nuevo ámbito de metadatos o abrir uno existente.</span><span class="sxs-lookup"><span data-stu-id="0f5c2-104">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f5c2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0f5c2-105">Methods</span></span>  
  
|<span data-ttu-id="0f5c2-106">Método</span><span class="sxs-lookup"><span data-stu-id="0f5c2-106">Method</span></span>|<span data-ttu-id="0f5c2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f5c2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f5c2-108">Método DefineScope</span><span class="sxs-lookup"><span data-stu-id="0f5c2-108">DefineScope Method</span></span>](imetadatadispenser-definescope-method.md)|<span data-ttu-id="0f5c2-109">Crea un nuevo área en la memoria donde se pueden crear nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="0f5c2-109">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="0f5c2-110">OpenScope (Método)</span><span class="sxs-lookup"><span data-stu-id="0f5c2-110">OpenScope Method</span></span>](imetadatadispenser-openscope-method.md)|<span data-ttu-id="0f5c2-111">Abre un archivo en disco existente y asigna sus metadatos a la memoria.</span><span class="sxs-lookup"><span data-stu-id="0f5c2-111">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="0f5c2-112">Método OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="0f5c2-112">OpenScopeOnMemory Method</span></span>](imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="0f5c2-113">Abre un área de memoria que contiene los metadatos existentes.</span><span class="sxs-lookup"><span data-stu-id="0f5c2-113">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="0f5c2-114">Es decir, este método abre un área de memoria especificada en la que los datos existentes se tratan como metadatos.</span><span class="sxs-lookup"><span data-stu-id="0f5c2-114">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f5c2-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f5c2-115">Requirements</span></span>  

 <span data-ttu-id="0f5c2-116">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f5c2-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f5c2-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0f5c2-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f5c2-118">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f5c2-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f5c2-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f5c2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f5c2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f5c2-120">See also</span></span>

- [<span data-ttu-id="0f5c2-121">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f5c2-121">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="0f5c2-122">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="0f5c2-122">Metadata Interfaces</span></span>](metadata-interfaces.md)
