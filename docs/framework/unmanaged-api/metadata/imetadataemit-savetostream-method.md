---
title: IMetaDataEmit::SaveToStream (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f6b5582b96dfc83eed482def2c4c4abfeb33a4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207791"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="85aec-102">IMetaDataEmit::SaveToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="85aec-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="85aec-103">Guarda todos los metadatos en el ámbito actual a los especificados `IStream`.</span><span class="sxs-lookup"><span data-stu-id="85aec-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85aec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85aec-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85aec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85aec-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="85aec-106">[in] La secuencia de escritura para guardar en.</span><span class="sxs-lookup"><span data-stu-id="85aec-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="85aec-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="85aec-107">[in] Reserved.</span></span> <span data-ttu-id="85aec-108">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="85aec-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85aec-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85aec-109">Requirements</span></span>  
 <span data-ttu-id="85aec-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85aec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85aec-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="85aec-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85aec-112">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85aec-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85aec-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85aec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85aec-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="85aec-114">See also</span></span>

- [<span data-ttu-id="85aec-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85aec-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="85aec-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85aec-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
