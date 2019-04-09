---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 812794bc76d475c516effdc950ca6a0b877494c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178365"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="dcc9a-102">IMetaDataTables::GetGuidHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="dcc9a-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="dcc9a-103">Obtiene el tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="dcc9a-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc9a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dcc9a-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcc9a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dcc9a-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="dcc9a-106">[out] Un puntero al tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="dcc9a-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcc9a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcc9a-107">Requirements</span></span>  
 <span data-ttu-id="dcc9a-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcc9a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcc9a-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="dcc9a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dcc9a-110">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dcc9a-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="dcc9a-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dcc9a-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dcc9a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcc9a-112">See also</span></span>

- [<span data-ttu-id="dcc9a-113">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dcc9a-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="dcc9a-114">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dcc9a-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
