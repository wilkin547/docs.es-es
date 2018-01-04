---
title: IMetaDataError (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError
helpviewer_keywords: IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4df7aa7400a180151de5420effc8738955d51c26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="70215-102">IMetaDataError (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="70215-102">IMetaDataError Interface</span></span>
<span data-ttu-id="70215-103">Proporciona un mecanismo de devolución de llamada para notificar errores durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="70215-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70215-104">El `IMetaDataError` debe implementar la interfaz por el cliente.</span><span class="sxs-lookup"><span data-stu-id="70215-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70215-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="70215-105">Methods</span></span>  
  
|<span data-ttu-id="70215-106">Método</span><span class="sxs-lookup"><span data-stu-id="70215-106">Method</span></span>|<span data-ttu-id="70215-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="70215-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70215-108">OnError (método)</span><span class="sxs-lookup"><span data-stu-id="70215-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="70215-109">Proporciona una notificación de errores que se producen durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="70215-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70215-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70215-110">Requirements</span></span>  
 <span data-ttu-id="70215-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70215-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70215-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="70215-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70215-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70215-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70215-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70215-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70215-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="70215-115">See Also</span></span>  
 [<span data-ttu-id="70215-116">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="70215-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
