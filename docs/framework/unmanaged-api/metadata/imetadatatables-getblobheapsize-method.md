---
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
ms.openlocfilehash: c32407c3fc0bc5a045b80ec48937699826d981af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177157"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="bd939-102">IMetaDataTables::GetBlobHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="bd939-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="bd939-103">Obtiene el tamaño, en bytes, del montón de objetos binarios grandes (BLOB).</span><span class="sxs-lookup"><span data-stu-id="bd939-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd939-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd939-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="bd939-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd939-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="bd939-106">[fuera] Un puntero al tamaño, en bytes, del montón BLOB.</span><span class="sxs-lookup"><span data-stu-id="bd939-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd939-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd939-107">Requirements</span></span>  
 <span data-ttu-id="bd939-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd939-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd939-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd939-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd939-110">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd939-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd939-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd939-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd939-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd939-112">See also</span></span>

- [<span data-ttu-id="bd939-113">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd939-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="bd939-114">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd939-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
