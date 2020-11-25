---
title: IMetaDataError (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
ms.openlocfilehash: 5f5e04787ce0ab0e1c8ecf3c19ba37e76ba38bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701931"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="14045-102">IMetaDataError (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14045-102">IMetaDataError Interface</span></span>

<span data-ttu-id="14045-103">Proporciona un mecanismo de devolución de llamada para notificar los errores durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="14045-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14045-104">El `IMetaDataError` cliente debe implementar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="14045-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14045-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="14045-105">Methods</span></span>  
  
|<span data-ttu-id="14045-106">Método</span><span class="sxs-lookup"><span data-stu-id="14045-106">Method</span></span>|<span data-ttu-id="14045-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="14045-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14045-108">Método OnError</span><span class="sxs-lookup"><span data-stu-id="14045-108">OnError Method</span></span>](imetadataerror-onerror-method.md)|<span data-ttu-id="14045-109">Proporciona una notificación de los errores que se producen durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="14045-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14045-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14045-110">Requirements</span></span>  

 <span data-ttu-id="14045-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14045-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14045-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="14045-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="14045-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="14045-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="14045-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14045-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14045-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14045-115">See also</span></span>

- [<span data-ttu-id="14045-116">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="14045-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
