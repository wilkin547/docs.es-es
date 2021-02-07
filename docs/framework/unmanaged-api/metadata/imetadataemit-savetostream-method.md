---
description: 'Más información sobre: IMetaDataEmit:: SaveToStream ((método)'
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
ms.openlocfilehash: 104aa0b0dfcd0f4f9e8b87b4633880f6423f92d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706661"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="9be77-103">IMetaDataEmit::SaveToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="9be77-103">IMetaDataEmit::SaveToStream Method</span></span>

<span data-ttu-id="9be77-104">Guarda todos los metadatos del ámbito actual en el especificado `IStream` .</span><span class="sxs-lookup"><span data-stu-id="9be77-104">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9be77-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9be77-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9be77-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9be77-106">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="9be77-107">de Secuencia grabable en la que se va a guardar.</span><span class="sxs-lookup"><span data-stu-id="9be77-107">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="9be77-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="9be77-108">[in] Reserved.</span></span> <span data-ttu-id="9be77-109">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="9be77-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9be77-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9be77-110">Requirements</span></span>  

 <span data-ttu-id="9be77-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9be77-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9be77-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9be77-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9be77-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9be77-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9be77-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9be77-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be77-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9be77-115">See also</span></span>

- [<span data-ttu-id="9be77-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9be77-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9be77-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9be77-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
