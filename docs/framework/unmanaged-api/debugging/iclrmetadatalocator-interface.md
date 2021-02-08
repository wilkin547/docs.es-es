---
description: 'Más información acerca de: interfaz Iclrmetadatalocator ('
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
ms.openlocfilehash: 6e7fd45197294563e12da020379d1bd54b088698
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772628"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="d7f99-103">ICLRMetadataLocator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7f99-103">ICLRMetadataLocator Interface</span></span>

<span data-ttu-id="d7f99-104">Lo utiliza el nivel de servicios de acceso a datos para buscar metadatos de ensamblados en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d7f99-104">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7f99-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d7f99-105">Methods</span></span>  
  
|<span data-ttu-id="d7f99-106">Método</span><span class="sxs-lookup"><span data-stu-id="d7f99-106">Method</span></span>|<span data-ttu-id="d7f99-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7f99-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7f99-108">GetMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="d7f99-108">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="d7f99-109">Recupera los metadatos de una imagen del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d7f99-109">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7f99-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d7f99-110">Remarks</span></span>  

 <span data-ttu-id="d7f99-111">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="d7f99-111">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="d7f99-112">Por ejemplo, la implementación de un proceso activo sería diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="d7f99-112">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f99-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7f99-113">Requirements</span></span>  

 <span data-ttu-id="d7f99-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7f99-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f99-115">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="d7f99-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d7f99-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7f99-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7f99-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f99-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f99-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7f99-118">See also</span></span>

- [<span data-ttu-id="d7f99-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d7f99-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
