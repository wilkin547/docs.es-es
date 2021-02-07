---
description: 'Más información acerca de: IMetaDataTables:: Getguidheapsize ((método)'
title: IMetaDataTables::GetGuidHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
ms.openlocfilehash: bbf2fd7e083c5a0a42ad69ab685b3e1aa8321d68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688148"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="09c45-103">IMetaDataTables::GetGuidHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="09c45-103">IMetaDataTables::GetGuidHeapSize Method</span></span>

<span data-ttu-id="09c45-104">Obtiene el tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="09c45-104">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09c45-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09c45-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09c45-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09c45-106">Parameters</span></span>  

 `pcbGuids`  
 <span data-ttu-id="09c45-107">enuncia Puntero al tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="09c45-107">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09c45-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09c45-108">Requirements</span></span>  

 <span data-ttu-id="09c45-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09c45-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09c45-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="09c45-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09c45-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09c45-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09c45-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09c45-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c45-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="09c45-113">See also</span></span>

- [<span data-ttu-id="09c45-114">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09c45-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="09c45-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09c45-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
