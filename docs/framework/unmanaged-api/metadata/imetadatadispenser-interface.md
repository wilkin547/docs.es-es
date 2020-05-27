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
ms.openlocfilehash: 2bdfe65dbf923ec61d91a259b5257d892fef53da
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007343"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="3eb65-102">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3eb65-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="3eb65-103">Proporciona métodos para crear un nuevo ámbito de metadatos o abrir uno existente.</span><span class="sxs-lookup"><span data-stu-id="3eb65-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3eb65-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3eb65-104">Methods</span></span>  
  
|<span data-ttu-id="3eb65-105">Método</span><span class="sxs-lookup"><span data-stu-id="3eb65-105">Method</span></span>|<span data-ttu-id="3eb65-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3eb65-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3eb65-107">Método DefineScope</span><span class="sxs-lookup"><span data-stu-id="3eb65-107">DefineScope Method</span></span>](imetadatadispenser-definescope-method.md)|<span data-ttu-id="3eb65-108">Crea un nuevo área en la memoria donde se pueden crear nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="3eb65-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="3eb65-109">Método OpenScope</span><span class="sxs-lookup"><span data-stu-id="3eb65-109">OpenScope Method</span></span>](imetadatadispenser-openscope-method.md)|<span data-ttu-id="3eb65-110">Abre un archivo en disco existente y asigna sus metadatos a la memoria.</span><span class="sxs-lookup"><span data-stu-id="3eb65-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="3eb65-111">Método OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="3eb65-111">OpenScopeOnMemory Method</span></span>](imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="3eb65-112">Abre un área de memoria que contiene los metadatos existentes.</span><span class="sxs-lookup"><span data-stu-id="3eb65-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="3eb65-113">Es decir, este método abre un área de memoria especificada en la que los datos existentes se tratan como metadatos.</span><span class="sxs-lookup"><span data-stu-id="3eb65-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3eb65-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3eb65-114">Requirements</span></span>  
 <span data-ttu-id="3eb65-115">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eb65-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb65-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3eb65-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3eb65-117">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3eb65-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3eb65-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb65-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb65-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3eb65-119">See also</span></span>

- [<span data-ttu-id="3eb65-120">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3eb65-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="3eb65-121">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="3eb65-121">Metadata Interfaces</span></span>](metadata-interfaces.md)
