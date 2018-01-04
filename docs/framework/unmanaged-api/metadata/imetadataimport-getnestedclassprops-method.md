---
title: "IMetaDataImport::GetNestedClassProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNestedClassProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8bbfe382a9a2fdf8ece1015ee73c3d9ef604ec7e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="36be0-102">IMetaDataImport::GetNestedClassProps (Método)</span><span class="sxs-lookup"><span data-stu-id="36be0-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="36be0-103">Obtiene la definición de tipo (token) para el elemento primario <xref:System.Type> del elemento especificado de tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="36be0-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36be0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36be0-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36be0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36be0-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="36be0-106">[in] Una definición de tipo símbolo (token) que representa el <xref:System.Type> para devolver la clase primaria símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="36be0-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="36be0-107">[out] Un puntero al token de TypeDef para el <xref:System.Type> que `tdNestedClass` está anidado en.</span><span class="sxs-lookup"><span data-stu-id="36be0-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36be0-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36be0-108">Requirements</span></span>  
 <span data-ttu-id="36be0-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36be0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36be0-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36be0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36be0-111">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36be0-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36be0-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36be0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36be0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="36be0-113">See Also</span></span>  
 [<span data-ttu-id="36be0-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36be0-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="36be0-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36be0-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
