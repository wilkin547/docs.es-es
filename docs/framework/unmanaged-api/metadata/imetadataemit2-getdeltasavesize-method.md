---
title: IMetaDataEmit2::GetDeltaSaveSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb59fdb2249d798c70b1990a6bca41c5c14b80c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610573"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="ac898-102">IMetaDataEmit2::GetDeltaSaveSize (Método)</span><span class="sxs-lookup"><span data-stu-id="ac898-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="ac898-103">Obtiene un valor que indica cualquier cambio en el tamaño de los metadatos que da como resultado de la sesión actual de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="ac898-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac898-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac898-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac898-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac898-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="ac898-106">[in] Uno de los [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) valores, que indica el nivel de precisión deseado.</span><span class="sxs-lookup"><span data-stu-id="ac898-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="ac898-107">Para la versión 2.0 de .NET Framework, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="ac898-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="ac898-108">[out] El cambio en el tamaño de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ac898-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac898-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac898-109">Requirements</span></span>  
 <span data-ttu-id="ac898-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac898-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac898-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ac898-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac898-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac898-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac898-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac898-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac898-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac898-114">See also</span></span>
- [<span data-ttu-id="ac898-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac898-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="ac898-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac898-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
