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
ms.openlocfilehash: 69897a7b646eb9f58e6b38588e302287b4241779
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043685"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="0da2b-102">IMetaDataEmit2::GetDeltaSaveSize (Método)</span><span class="sxs-lookup"><span data-stu-id="0da2b-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="0da2b-103">Obtiene un valor que indica cualquier cambio en el tamaño de los metadatos que da como resultado de la sesión actual de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="0da2b-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0da2b-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da2b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0da2b-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="0da2b-106">[in] Uno de los [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) valores, que indica el nivel de precisión deseado.</span><span class="sxs-lookup"><span data-stu-id="0da2b-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="0da2b-107">Para la versión 2.0 de .NET Framework, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="0da2b-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="0da2b-108">[out] El cambio en el tamaño de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="0da2b-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da2b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0da2b-109">Requirements</span></span>  
 <span data-ttu-id="0da2b-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0da2b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da2b-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="0da2b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0da2b-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0da2b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0da2b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0da2b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da2b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0da2b-114">See also</span></span>

- [<span data-ttu-id="0da2b-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0da2b-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="0da2b-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0da2b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
