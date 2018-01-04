---
title: "IMetaDataImport::GetTypeRefProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetTypeRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 23dbfe2468088da5e02fb7156606af5f3fa51044
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="17d35-102">IMetaDataImport::GetTypeRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="17d35-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="17d35-103">Obtiene los metadatos asociados con el <xref:System.Type> al que hace referencia el token de TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="17d35-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17d35-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17d35-104">Syntax</span></span>  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17d35-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17d35-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="17d35-106">[in] Símbolo (token) de TypeRef que representa el tipo para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="17d35-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="17d35-107">[out] Un puntero al ámbito en el que se hace la referencia.</span><span class="sxs-lookup"><span data-stu-id="17d35-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="17d35-108">Este valor es un símbolo (token) AssemblyRef o de ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="17d35-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="17d35-109">[out] Un búfer que contiene el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="17d35-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="17d35-110">[in] El tamaño solicitado en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="17d35-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="17d35-111">[out] El tamaño devuelto en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="17d35-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17d35-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17d35-112">Requirements</span></span>  
 <span data-ttu-id="17d35-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17d35-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17d35-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="17d35-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="17d35-115">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17d35-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="17d35-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17d35-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d35-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="17d35-117">See Also</span></span>  
 [<span data-ttu-id="17d35-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17d35-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="17d35-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17d35-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
