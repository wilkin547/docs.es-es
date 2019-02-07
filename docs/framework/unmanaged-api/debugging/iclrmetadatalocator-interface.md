---
title: ICLRMetadataLocator (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5dd77783c03d6a61d0b5831e44db97a731d8074
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825893"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="bb3d2-102">ICLRMetadataLocator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb3d2-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="bb3d2-103">Usa la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb3d2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bb3d2-104">Methods</span></span>  
  
|<span data-ttu-id="bb3d2-105">Método</span><span class="sxs-lookup"><span data-stu-id="bb3d2-105">Method</span></span>|<span data-ttu-id="bb3d2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb3d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb3d2-107">GetMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="bb3d2-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="bb3d2-108">Recupera los metadatos de una imagen del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb3d2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb3d2-109">Remarks</span></span>  
 <span data-ttu-id="bb3d2-110">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="bb3d2-111">Por ejemplo, la implementación de un proceso activo sería diferente de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="bb3d2-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb3d2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb3d2-112">Requirements</span></span>  
 <span data-ttu-id="bb3d2-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb3d2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb3d2-114">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="bb3d2-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bb3d2-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb3d2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb3d2-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb3d2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3d2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb3d2-117">See also</span></span>
- [<span data-ttu-id="bb3d2-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bb3d2-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
