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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d97f536d54ac1cb77c5d0413d2437508374ac7f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169005"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="3c293-102">IMetaDataEmit2::SaveDelta (Método)</span><span class="sxs-lookup"><span data-stu-id="3c293-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="3c293-103">Guarda los cambios de la sesión actual de editar y continuar en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="3c293-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c293-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c293-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c293-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c293-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="3c293-106">[in] El nombre de archivo en el que se va a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="3c293-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="3c293-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="3c293-107">[in] Reserved.</span></span> <span data-ttu-id="3c293-108">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="3c293-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c293-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c293-109">Requirements</span></span>  
 <span data-ttu-id="3c293-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c293-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c293-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c293-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c293-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c293-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c293-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c293-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c293-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c293-114">See also</span></span>

- [<span data-ttu-id="3c293-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c293-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="3c293-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c293-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
