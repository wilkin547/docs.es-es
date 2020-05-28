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
ms.openlocfilehash: 87e00a69643b6bc403188fb0fdb6f9e3f3d82115
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003885"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="77a16-102">IMetaDataEmit::SaveToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="77a16-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="77a16-103">Guarda todos los metadatos del ámbito actual en el especificado `IStream` .</span><span class="sxs-lookup"><span data-stu-id="77a16-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77a16-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77a16-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77a16-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="77a16-106">de Secuencia grabable en la que se va a guardar.</span><span class="sxs-lookup"><span data-stu-id="77a16-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="77a16-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="77a16-107">[in] Reserved.</span></span> <span data-ttu-id="77a16-108">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="77a16-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77a16-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77a16-109">Requirements</span></span>  
 <span data-ttu-id="77a16-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77a16-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77a16-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="77a16-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77a16-112">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="77a16-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77a16-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77a16-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a16-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77a16-114">See also</span></span>

- [<span data-ttu-id="77a16-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="77a16-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="77a16-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="77a16-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
