---
title: "IMetaDataImport::GetTypeDefProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1025ffde2bd066c81c4c562c0dd86e829fc2aef3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="ea109-102">IMetaDataImport::GetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="ea109-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="ea109-103">Devuelve información de metadatos para el <xref:System.Type> representado por el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="ea109-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea109-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea109-104">Syntax</span></span>  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea109-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea109-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ea109-106">[in] El token de TypeDef que representa el tipo para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ea109-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="ea109-107">[out] Un búfer que contiene el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="ea109-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="ea109-108">[in] El tamaño en caracteres anchos de `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="ea109-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="ea109-109">[out] El número de caracteres anchos devueltos en `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="ea109-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="ea109-110">[out] Puntero a cualquier marcador que modifique la definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="ea109-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="ea109-111">Este valor es una máscara de bits de la [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="ea109-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="ea109-112">[out] Un token de metadatos de TypeDef o TypeRef que representa el tipo base del tipo solicitado.</span><span class="sxs-lookup"><span data-stu-id="ea109-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea109-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea109-113">Requirements</span></span>  
 <span data-ttu-id="ea109-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea109-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea109-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea109-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea109-116">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea109-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea109-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea109-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea109-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea109-118">See Also</span></span>  
 [<span data-ttu-id="ea109-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea109-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ea109-120">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea109-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
