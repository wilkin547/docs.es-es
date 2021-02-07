---
description: 'Más información acerca de: IMetaDataTables:: Getblobheapsize ((método)'
title: IMetaDataTables::GetBlobHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
ms.openlocfilehash: f6d5c7aeb5e1cc1f307d53d8f3e3cc99daa72311
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688317"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="19da4-103">IMetaDataTables::GetBlobHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="19da4-103">IMetaDataTables::GetBlobHeapSize Method</span></span>

<span data-ttu-id="19da4-104">Obtiene el tamaño, en bytes, del montón de objetos binarios grandes (BLOB).</span><span class="sxs-lookup"><span data-stu-id="19da4-104">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19da4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19da4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="19da4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19da4-106">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="19da4-107">enuncia Puntero al tamaño, en bytes, del montón de BLOBs.</span><span class="sxs-lookup"><span data-stu-id="19da4-107">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19da4-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19da4-108">Requirements</span></span>  

 <span data-ttu-id="19da4-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19da4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19da4-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="19da4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="19da4-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19da4-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19da4-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19da4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19da4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="19da4-113">See also</span></span>

- [<span data-ttu-id="19da4-114">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19da4-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="19da4-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19da4-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
