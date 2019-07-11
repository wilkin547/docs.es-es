---
title: IMetaDataError::OnError (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42cc0896dce713daed310f07d39a02bfb7386030
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777091"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="b8dc3-102">IMetaDataError::OnError (Método)</span><span class="sxs-lookup"><span data-stu-id="b8dc3-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="b8dc3-103">Proporciona notificación de errores que se producen durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="b8dc3-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8dc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8dc3-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8dc3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8dc3-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="b8dc3-106">[in] Devuelve el valor de error HRESULT al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="b8dc3-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="b8dc3-107">[in] El token de metadatos del objeto de código que se combinan cuando se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="b8dc3-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8dc3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8dc3-108">Requirements</span></span>  
 <span data-ttu-id="b8dc3-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8dc3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8dc3-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b8dc3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8dc3-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8dc3-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8dc3-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8dc3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8dc3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8dc3-113">See also</span></span>

- [<span data-ttu-id="b8dc3-114">IMetaDataError (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8dc3-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
