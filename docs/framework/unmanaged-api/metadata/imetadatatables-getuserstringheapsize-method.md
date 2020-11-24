---
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
ms.openlocfilehash: 048010f00f6581a29c6b1a3150bf5ae8822b5664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672466"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="444f7-102">IMetaDataTables::GetUserStringHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="444f7-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>

<span data-ttu-id="444f7-103">Obtiene el tamaño, en bytes, del montón de cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="444f7-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="444f7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="444f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="444f7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="444f7-105">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="444f7-106">enuncia Puntero al tamaño, en bytes, del montón de cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="444f7-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="444f7-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="444f7-107">Requirements</span></span>  

 <span data-ttu-id="444f7-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="444f7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="444f7-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="444f7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="444f7-110">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="444f7-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="444f7-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="444f7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="444f7-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="444f7-112">See also</span></span>

- [<span data-ttu-id="444f7-113">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="444f7-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="444f7-114">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="444f7-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
