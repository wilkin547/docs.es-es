---
description: 'Más información acerca de: IMetaDataTables:: Getnextblob ((método)'
title: IMetaDataTables::GetNextBlob (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
ms.openlocfilehash: 99126ab5c3891ee09346bb54096a4fce3ca44bc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688135"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="b356e-103">IMetaDataTables::GetNextBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="b356e-103">IMetaDataTables::GetNextBlob Method</span></span>

<span data-ttu-id="b356e-104">Obtiene el índice del siguiente objeto binario grande (BLOB) de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b356e-104">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b356e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b356e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b356e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b356e-106">Parameters</span></span>  

 `ixBlob`  
 <span data-ttu-id="b356e-107">de Índice, tal y como se devuelve de una columna de blobs.</span><span class="sxs-lookup"><span data-stu-id="b356e-107">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="b356e-108">enuncia Puntero al índice del siguiente BLOB.</span><span class="sxs-lookup"><span data-stu-id="b356e-108">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b356e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b356e-109">Requirements</span></span>  

 <span data-ttu-id="b356e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b356e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b356e-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b356e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b356e-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b356e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b356e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b356e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b356e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b356e-114">See also</span></span>

- [<span data-ttu-id="b356e-115">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b356e-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b356e-116">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b356e-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
