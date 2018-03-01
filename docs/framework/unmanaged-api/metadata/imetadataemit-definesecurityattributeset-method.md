---
title: "IMetaDataEmit::DefineSecurityAttributeSet (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4863ee416bba7fe66326c1d11ec3aa0037d022a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="6a8a8-102">IMetaDataEmit::DefineSecurityAttributeSet (Método)</span><span class="sxs-lookup"><span data-stu-id="6a8a8-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="6a8a8-103">Crea un conjunto de permisos de seguridad para adjuntar al objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="6a8a8-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a8a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a8a8-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a8a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a8a8-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="6a8a8-106">[in] El token al que se adjunta la información de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6a8a8-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="6a8a8-107">[in] Una matriz de `COR_SECATTR` estructuras.</span><span class="sxs-lookup"><span data-stu-id="6a8a8-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="6a8a8-108">[in] El número de elementos de `rSecAttrs`.</span><span class="sxs-lookup"><span data-stu-id="6a8a8-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="6a8a8-109">[out] Si se produce un error en el método, especifica el índice en `rSecAttrs` del elemento que causó el problema.</span><span class="sxs-lookup"><span data-stu-id="6a8a8-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a8a8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a8a8-110">Requirements</span></span>  
 <span data-ttu-id="6a8a8-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a8a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a8a8-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a8a8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a8a8-113">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a8a8-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a8a8-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a8a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a8a8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a8a8-115">See Also</span></span>  
 [<span data-ttu-id="6a8a8-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a8a8-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="6a8a8-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a8a8-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
