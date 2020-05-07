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
ms.openlocfilehash: 734f8eaa7c520bbf1ad1208ece42751e967a208a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859721"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="110d0-102">ICLRMetadataLocator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="110d0-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="110d0-103">Lo utiliza el nivel de servicios de acceso a datos para buscar metadatos de ensamblados en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="110d0-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="110d0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="110d0-104">Methods</span></span>  
  
|<span data-ttu-id="110d0-105">Método</span><span class="sxs-lookup"><span data-stu-id="110d0-105">Method</span></span>|<span data-ttu-id="110d0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="110d0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="110d0-107">GetMetadata (método)</span><span class="sxs-lookup"><span data-stu-id="110d0-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="110d0-108">Recupera los metadatos de una imagen del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="110d0-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="110d0-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="110d0-109">Remarks</span></span>  
 <span data-ttu-id="110d0-110">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="110d0-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="110d0-111">Por ejemplo, la implementación de un proceso activo sería diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="110d0-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="110d0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="110d0-112">Requirements</span></span>  
 <span data-ttu-id="110d0-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="110d0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="110d0-114">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="110d0-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="110d0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="110d0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="110d0-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="110d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="110d0-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="110d0-117">See also</span></span>

- [<span data-ttu-id="110d0-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="110d0-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
