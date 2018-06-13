---
title: IMetaDataEmit::SetMethodProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ef6771ec3f458c20701cc330a5730367b3c5b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445931"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="a7dbb-102">IMetaDataEmit::SetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="a7dbb-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="a7dbb-103">Establece o actualiza la característica, almacenada en la dirección virtual relativa especificada, de un método definido por una llamada anterior a [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="a7dbb-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7dbb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7dbb-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7dbb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7dbb-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="a7dbb-106">[in] El token para el método que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="a7dbb-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="a7dbb-107">[in] Los atributos de miembro.</span><span class="sxs-lookup"><span data-stu-id="a7dbb-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="a7dbb-108">[in] La dirección del código.</span><span class="sxs-lookup"><span data-stu-id="a7dbb-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="a7dbb-109">[in] Los marcadores de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="a7dbb-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7dbb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7dbb-110">Requirements</span></span>  
 <span data-ttu-id="a7dbb-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7dbb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7dbb-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7dbb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7dbb-113">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7dbb-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7dbb-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7dbb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7dbb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7dbb-115">See Also</span></span>  
 [<span data-ttu-id="a7dbb-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7dbb-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a7dbb-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7dbb-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
