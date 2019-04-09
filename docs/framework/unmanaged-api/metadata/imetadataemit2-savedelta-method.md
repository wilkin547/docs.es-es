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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169005"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="5b472-102">IMetaDataEmit2::SaveDelta (Método)</span><span class="sxs-lookup"><span data-stu-id="5b472-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="5b472-103">Guarda los cambios de la sesión actual de editar y continuar en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="5b472-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b472-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b472-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b472-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5b472-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="5b472-106">[in] El nombre de archivo en el que se va a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="5b472-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="5b472-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="5b472-107">[in] Reserved.</span></span> <span data-ttu-id="5b472-108">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="5b472-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b472-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b472-109">Requirements</span></span>  
 <span data-ttu-id="5b472-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b472-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b472-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b472-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b472-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b472-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5b472-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5b472-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b472-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b472-114">See also</span></span>

- [<span data-ttu-id="5b472-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b472-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="5b472-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b472-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
