---
title: IMetaDataEmit2::SaveDeltaToMemory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: a4dbe090987248ef77ce371b5bc6fb42d898f726
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705415"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="08f72-102">IMetaDataEmit2::SaveDeltaToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="08f72-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>

<span data-ttu-id="08f72-103">Guarda los cambios de la sesión de edición y continuación actual en la memoria.</span><span class="sxs-lookup"><span data-stu-id="08f72-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08f72-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08f72-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08f72-105">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="08f72-106">enuncia Dirección en la que se va a comenzar a escribir la diferencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="08f72-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="08f72-107">de Tamaño de los cambios.</span><span class="sxs-lookup"><span data-stu-id="08f72-107">[in] The size of the changes.</span></span> <span data-ttu-id="08f72-108">Use [IMetaDataEmit2:: GetDeltaSaveSize (](imetadataemit2-getdeltasavesize-method.md) para determinar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="08f72-108">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f72-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08f72-109">Requirements</span></span>  

 <span data-ttu-id="08f72-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08f72-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f72-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="08f72-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08f72-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08f72-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08f72-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08f72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f72-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08f72-114">See also</span></span>

- [<span data-ttu-id="08f72-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08f72-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="08f72-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08f72-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
