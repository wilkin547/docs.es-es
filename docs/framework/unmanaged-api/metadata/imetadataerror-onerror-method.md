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
ms.openlocfilehash: 1ed9e097dccd0fcb81ea9023cc9b84906589ccb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446263"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="4f98e-102">IMetaDataError::OnError (Método)</span><span class="sxs-lookup"><span data-stu-id="4f98e-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="4f98e-103">Proporciona una notificación de errores que se producen durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4f98e-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f98e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f98e-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f98e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f98e-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="4f98e-106">[in] El valor de error HRESULT devuelto para el método de llamada.</span><span class="sxs-lookup"><span data-stu-id="4f98e-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="4f98e-107">[in] El token de metadatos del objeto de código que se estaba combinando cuando se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="4f98e-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f98e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f98e-108">Requirements</span></span>  
 <span data-ttu-id="4f98e-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f98e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f98e-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4f98e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f98e-111">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f98e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f98e-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f98e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f98e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f98e-113">See Also</span></span>  
 [<span data-ttu-id="4f98e-114">IMetaDataError (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f98e-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
