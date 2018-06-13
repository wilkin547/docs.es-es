---
title: IMetaDataEmit::SetMethodImplFlags (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71881fe8c4b883bb91468033a3c17c8d77c35f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445427"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="77b64-102">IMetaDataEmit::SetMethodImplFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="77b64-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="77b64-103">Establece o actualiza la firma de metadatos de la implementación del método heredado que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="77b64-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77b64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77b64-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77b64-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77b64-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="77b64-106">[in] El token para el método que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="77b64-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="77b64-107">[in] Una combinación de los valores de la [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeración que especifica las características de implementación de método.</span><span class="sxs-lookup"><span data-stu-id="77b64-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77b64-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77b64-108">Requirements</span></span>  
 <span data-ttu-id="77b64-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77b64-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77b64-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77b64-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77b64-111">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77b64-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77b64-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77b64-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b64-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="77b64-113">See Also</span></span>  
 [<span data-ttu-id="77b64-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="77b64-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="77b64-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="77b64-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
