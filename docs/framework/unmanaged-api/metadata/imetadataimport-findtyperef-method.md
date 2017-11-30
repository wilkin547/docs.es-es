---
title: "IMetaDataImport::FindTypeRef (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindTypeRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d742033788e270f01ee0cea70569ca65e7f35697
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="6d916-102">IMetaDataImport::FindTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="6d916-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="6d916-103">Obtiene un puntero al TypeRef token para el <xref:System.Type> referencia que se encuentra en el ámbito especificado y que tiene el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="6d916-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d916-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d916-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d916-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d916-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="6d916-106">[in] Símbolo (token) de ModuleRef, AssemblyRef o TypeRef que especifica el módulo, un ensamblado o un tipo, respectivamente, en que el tipo de referencia se define.</span><span class="sxs-lookup"><span data-stu-id="6d916-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="6d916-107">[in] El nombre de la referencia de tipo que se buscará.</span><span class="sxs-lookup"><span data-stu-id="6d916-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="6d916-108">[out] Un puntero al token de TypeRef correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6d916-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d916-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d916-109">Requirements</span></span>  
 <span data-ttu-id="6d916-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d916-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d916-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6d916-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d916-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d916-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d916-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d916-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d916-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d916-114">See Also</span></span>  
 [<span data-ttu-id="6d916-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d916-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="6d916-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d916-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
