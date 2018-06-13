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
ms.openlocfilehash: 1c264bfd31f8cd31bacf2d194ddbd07338569294
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447175"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="0ad7a-102">IMetaDataError (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ad7a-102">IMetaDataError Interface</span></span>
<span data-ttu-id="0ad7a-103">Proporciona un mecanismo de devolución de llamada para notificar errores durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ad7a-104">El `IMetaDataError` debe implementar la interfaz por el cliente.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ad7a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0ad7a-105">Methods</span></span>  
  
|<span data-ttu-id="0ad7a-106">Método</span><span class="sxs-lookup"><span data-stu-id="0ad7a-106">Method</span></span>|<span data-ttu-id="0ad7a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ad7a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ad7a-108">OnError (método)</span><span class="sxs-lookup"><span data-stu-id="0ad7a-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="0ad7a-109">Proporciona una notificación de errores que se producen durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="0ad7a-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ad7a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ad7a-110">Requirements</span></span>  
 <span data-ttu-id="0ad7a-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad7a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad7a-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ad7a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ad7a-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ad7a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ad7a-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad7a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad7a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ad7a-115">See Also</span></span>  
 [<span data-ttu-id="0ad7a-116">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="0ad7a-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
