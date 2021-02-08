---
description: 'Más información sobre: IMetaDataEmit2:: Savedeltatostream ((método)'
title: IMetaDataEmit2::SaveDeltaToStream (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: ce2e7822a5220a8ab1264a6e18337ba0f7828e3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771709"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="ff771-103">IMetaDataEmit2::SaveDeltaToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="ff771-103">IMetaDataEmit2::SaveDeltaToStream Method</span></span>

<span data-ttu-id="ff771-104">Guarda los cambios de la sesión de edición y continuación actual en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="ff771-104">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff771-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff771-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff771-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff771-106">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="ff771-107">de Puntero de interfaz a la secuencia de escritura en la que se van a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="ff771-107">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="ff771-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="ff771-108">[in] Reserved.</span></span> <span data-ttu-id="ff771-109">Este valor debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="ff771-109">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff771-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff771-110">Requirements</span></span>  

 <span data-ttu-id="ff771-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff771-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff771-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ff771-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff771-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff771-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ff771-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff771-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff771-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff771-115">See also</span></span>

- [<span data-ttu-id="ff771-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff771-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="ff771-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff771-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
