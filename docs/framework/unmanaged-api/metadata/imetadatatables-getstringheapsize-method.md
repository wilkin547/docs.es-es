---
title: IMetaDataTables::GetStringHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
ms.openlocfilehash: 1aa7853602c1aaf484ef89d9c4fb06464e135f80
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501182"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="b3440-102">IMetaDataTables::GetStringHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="b3440-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="b3440-103">Obtiene el tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="b3440-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3440-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3440-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3440-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3440-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="b3440-106">enuncia Puntero al tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="b3440-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3440-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3440-107">Requirements</span></span>  
 <span data-ttu-id="b3440-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3440-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3440-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b3440-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3440-110">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b3440-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3440-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3440-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3440-112">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="b3440-112">See also</span></span>

- [<span data-ttu-id="b3440-113">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3440-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b3440-114">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3440-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
