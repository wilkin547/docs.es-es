---
title: IMetaDataEmit2::SaveDelta (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: ab2f30c485a755d4788926c13c2608e55a716c5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704271"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="0fef2-102">IMetaDataEmit2::SaveDelta (Método)</span><span class="sxs-lookup"><span data-stu-id="0fef2-102">IMetaDataEmit2::SaveDelta Method</span></span>

<span data-ttu-id="0fef2-103">Guarda los cambios de la sesión de edición y continuación actual en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="0fef2-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fef2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fef2-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fef2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fef2-105">Parameters</span></span>  

 `szFile`  
 <span data-ttu-id="0fef2-106">de Nombre del archivo en el que se van a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="0fef2-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="0fef2-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="0fef2-107">[in] Reserved.</span></span> <span data-ttu-id="0fef2-108">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="0fef2-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fef2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fef2-109">Requirements</span></span>  

 <span data-ttu-id="0fef2-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fef2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fef2-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0fef2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0fef2-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0fef2-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0fef2-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fef2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fef2-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0fef2-114">See also</span></span>

- [<span data-ttu-id="0fef2-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fef2-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="0fef2-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fef2-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
