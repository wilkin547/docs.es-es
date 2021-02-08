---
description: 'Más información sobre: IMetaDataEmit2:: SaveDeltaToMemory ((método)'
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
ms.openlocfilehash: 3ef01889df6dede85947508ca08635c95d655666
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771761"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="54382-103">IMetaDataEmit2::SaveDeltaToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="54382-103">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>

<span data-ttu-id="54382-104">Guarda los cambios de la sesión de edición y continuación actual en la memoria.</span><span class="sxs-lookup"><span data-stu-id="54382-104">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54382-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54382-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54382-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54382-106">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="54382-107">enuncia Dirección en la que se va a comenzar a escribir la diferencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="54382-107">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="54382-108">de Tamaño de los cambios.</span><span class="sxs-lookup"><span data-stu-id="54382-108">[in] The size of the changes.</span></span> <span data-ttu-id="54382-109">Use [IMetaDataEmit2:: GetDeltaSaveSize (](imetadataemit2-getdeltasavesize-method.md) para determinar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="54382-109">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54382-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54382-110">Requirements</span></span>  

 <span data-ttu-id="54382-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54382-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54382-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="54382-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54382-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54382-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54382-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54382-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54382-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="54382-115">See also</span></span>

- [<span data-ttu-id="54382-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="54382-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="54382-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="54382-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
