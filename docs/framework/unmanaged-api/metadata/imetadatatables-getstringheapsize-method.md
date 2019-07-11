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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b842fb4d0853f473ae8e237a42e800cf0af8dc11
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781382"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="d13bb-102">IMetaDataTables::GetStringHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="d13bb-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="d13bb-103">Obtiene el tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="d13bb-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d13bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d13bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d13bb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d13bb-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="d13bb-106">[out] Un puntero al tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="d13bb-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d13bb-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d13bb-107">Requirements</span></span>  
 <span data-ttu-id="d13bb-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d13bb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d13bb-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d13bb-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d13bb-110">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d13bb-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d13bb-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d13bb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d13bb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d13bb-112">See also</span></span>

- [<span data-ttu-id="d13bb-113">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d13bb-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="d13bb-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d13bb-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
