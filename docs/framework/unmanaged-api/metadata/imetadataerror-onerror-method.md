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
ms.openlocfilehash: 489fa217744e41ccb5d27d088790131c15e1ee52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177398"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="e57f2-102">IMetaDataError::OnError (Método)</span><span class="sxs-lookup"><span data-stu-id="e57f2-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="e57f2-103">Proporciona una notificación de los errores que se producen durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e57f2-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e57f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e57f2-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e57f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e57f2-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="e57f2-106">[en] El valor de error HRESULT devuelto al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="e57f2-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="e57f2-107">[en] El token de metadatos del objeto de código que se estaba combinando cuando se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="e57f2-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e57f2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e57f2-108">Requirements</span></span>  
 <span data-ttu-id="e57f2-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e57f2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e57f2-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e57f2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e57f2-111">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e57f2-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e57f2-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e57f2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57f2-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e57f2-113">See also</span></span>

- [<span data-ttu-id="e57f2-114">IMetaDataError (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e57f2-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
