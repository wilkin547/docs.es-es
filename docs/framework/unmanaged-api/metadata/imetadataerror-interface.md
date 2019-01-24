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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe2f683ae46d1ee6205f97536976a358e86fc53d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720384"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="4f8b0-102">IMetaDataError (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f8b0-102">IMetaDataError Interface</span></span>
<span data-ttu-id="4f8b0-103">Proporciona un mecanismo de devolución de llamada para notificar errores durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4f8b0-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f8b0-104">El `IMetaDataError` interfaz se debe implementar el cliente.</span><span class="sxs-lookup"><span data-stu-id="4f8b0-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f8b0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4f8b0-105">Methods</span></span>  
  
|<span data-ttu-id="4f8b0-106">Método</span><span class="sxs-lookup"><span data-stu-id="4f8b0-106">Method</span></span>|<span data-ttu-id="4f8b0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f8b0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f8b0-108">OnError (método)</span><span class="sxs-lookup"><span data-stu-id="4f8b0-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="4f8b0-109">Proporciona notificación de errores que se producen durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4f8b0-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f8b0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f8b0-110">Requirements</span></span>  
 <span data-ttu-id="4f8b0-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f8b0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f8b0-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="4f8b0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f8b0-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f8b0-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f8b0-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f8b0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8b0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f8b0-115">See also</span></span>
- [<span data-ttu-id="4f8b0-116">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="4f8b0-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
