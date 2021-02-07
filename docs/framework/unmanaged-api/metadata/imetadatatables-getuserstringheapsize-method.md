---
description: 'Más información acerca de: IMetaDataTables:: Getuserstringheapsize ((método)'
title: IMetaDataTables::GetUserStringHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
ms.openlocfilehash: 7e6f3eed7803f52e6bde888852c4971900f0868c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687628"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="5170a-103">IMetaDataTables::GetUserStringHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="5170a-103">IMetaDataTables::GetUserStringHeapSize Method</span></span>

<span data-ttu-id="5170a-104">Obtiene el tamaño, en bytes, del montón de cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="5170a-104">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5170a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5170a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5170a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5170a-106">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="5170a-107">enuncia Puntero al tamaño, en bytes, del montón de cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="5170a-107">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5170a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5170a-108">Requirements</span></span>  

 <span data-ttu-id="5170a-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5170a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5170a-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5170a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5170a-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5170a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5170a-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5170a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5170a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5170a-113">See also</span></span>

- [<span data-ttu-id="5170a-114">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5170a-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="5170a-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5170a-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
