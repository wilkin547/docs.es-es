---
description: 'Más información acerca de: IMetaDataEmit:: Save (método)'
title: IMetaDataEmit::Save (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: bf8675540ae2c851d2b6ed14883c9b75e9631903
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745871"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="8a008-103">IMetaDataEmit::Save (Método)</span><span class="sxs-lookup"><span data-stu-id="8a008-103">IMetaDataEmit::Save Method</span></span>

<span data-ttu-id="8a008-104">Guarda todos los metadatos en el ámbito actual en el archivo en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="8a008-104">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a008-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a008-105">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a008-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a008-106">Parameters</span></span>  

 `wzFile`  
 <span data-ttu-id="8a008-107">de Nombre del archivo en el que se va a guardar.</span><span class="sxs-lookup"><span data-stu-id="8a008-107">[in] The name of the file to save to.</span></span> <span data-ttu-id="8a008-108">Si este valor es null, la copia en memoria se guardará en la última ubicación utilizada.</span><span class="sxs-lookup"><span data-stu-id="8a008-108">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="8a008-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="8a008-109">[in] Reserved.</span></span> <span data-ttu-id="8a008-110">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="8a008-110">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a008-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a008-111">Requirements</span></span>  

 <span data-ttu-id="8a008-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a008-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a008-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8a008-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a008-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a008-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a008-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a008-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a008-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a008-116">See also</span></span>

- [<span data-ttu-id="8a008-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a008-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8a008-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a008-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
