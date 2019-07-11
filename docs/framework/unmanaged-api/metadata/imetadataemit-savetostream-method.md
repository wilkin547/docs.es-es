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
ms.openlocfilehash: 96b3b270fb12aa451d9026435dd3d2c4c196b09c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782026"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="f43c3-102">IMetaDataEmit::SaveToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="f43c3-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="f43c3-103">Guarda todos los metadatos en el ámbito actual a los especificados `IStream`.</span><span class="sxs-lookup"><span data-stu-id="f43c3-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f43c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f43c3-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f43c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f43c3-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="f43c3-106">[in] La secuencia de escritura para guardar en.</span><span class="sxs-lookup"><span data-stu-id="f43c3-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="f43c3-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="f43c3-107">[in] Reserved.</span></span> <span data-ttu-id="f43c3-108">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="f43c3-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f43c3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f43c3-109">Requirements</span></span>  
 <span data-ttu-id="f43c3-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f43c3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f43c3-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f43c3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f43c3-112">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f43c3-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f43c3-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f43c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43c3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f43c3-114">See also</span></span>

- [<span data-ttu-id="f43c3-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f43c3-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f43c3-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f43c3-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
