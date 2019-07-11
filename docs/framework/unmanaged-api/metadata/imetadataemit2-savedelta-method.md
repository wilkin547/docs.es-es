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
ms.openlocfilehash: 212625fd460e88201dd4799754297861826d3aa7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777146"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="aa6fd-102">IMetaDataEmit2::SaveDelta (Método)</span><span class="sxs-lookup"><span data-stu-id="aa6fd-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="aa6fd-103">Guarda los cambios de la sesión actual de editar y continuar en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="aa6fd-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa6fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa6fd-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa6fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa6fd-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="aa6fd-106">[in] El nombre de archivo en el que se va a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="aa6fd-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="aa6fd-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="aa6fd-107">[in] Reserved.</span></span> <span data-ttu-id="aa6fd-108">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="aa6fd-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa6fd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa6fd-109">Requirements</span></span>  
 <span data-ttu-id="aa6fd-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa6fd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa6fd-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa6fd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa6fd-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa6fd-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aa6fd-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa6fd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa6fd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa6fd-114">See also</span></span>

- [<span data-ttu-id="aa6fd-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa6fd-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="aa6fd-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa6fd-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
