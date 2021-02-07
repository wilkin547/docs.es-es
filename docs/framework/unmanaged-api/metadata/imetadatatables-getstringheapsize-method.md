---
description: 'Más información acerca de: IMetaDataTables:: GetStringHeapSize ((método)'
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
ms.openlocfilehash: 0ec9f4e2768cc78163db67bc9099fc9cafae8c8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687784"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="a62fd-103">IMetaDataTables::GetStringHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="a62fd-103">IMetaDataTables::GetStringHeapSize Method</span></span>

<span data-ttu-id="a62fd-104">Obtiene el tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="a62fd-104">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a62fd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a62fd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a62fd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a62fd-106">Parameters</span></span>  

 `pcbStrings`  
 <span data-ttu-id="a62fd-107">enuncia Puntero al tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="a62fd-107">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a62fd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a62fd-108">Requirements</span></span>  

 <span data-ttu-id="a62fd-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a62fd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a62fd-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a62fd-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a62fd-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a62fd-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a62fd-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a62fd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62fd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a62fd-113">See also</span></span>

- [<span data-ttu-id="a62fd-114">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a62fd-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="a62fd-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a62fd-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
