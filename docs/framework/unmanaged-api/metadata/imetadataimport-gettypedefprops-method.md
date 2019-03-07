---
title: IMetaDataImport::GetTypeDefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4994dedcaac26f06f605532cc4579c78f4e8366
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501349"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="e5d38-102">IMetaDataImport::GetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="e5d38-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="e5d38-103">Devuelve información de metadatos para el <xref:System.Type> representado por el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="e5d38-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5d38-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e5d38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5d38-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e5d38-106">[in] El token de TypeDef que representa el tipo para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="e5d38-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="e5d38-107">[out] Un búfer que contiene el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="e5d38-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="e5d38-108">[in] El tamaño en caracteres anchos de `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="e5d38-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="e5d38-109">[out] El número de caracteres anchos que se devuelven en `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="e5d38-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="e5d38-110">[out] Un puntero a cualquier marcador que modifique la definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="e5d38-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="e5d38-111">Este valor es una máscara de bits desde el [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="e5d38-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="e5d38-112">[out] Un token de metadatos de TypeDef o TypeRef que representa el tipo base del tipo solicitado.</span><span class="sxs-lookup"><span data-stu-id="e5d38-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5d38-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5d38-113">Requirements</span></span>  
 <span data-ttu-id="e5d38-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5d38-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d38-115">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e5d38-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5d38-116">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5d38-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5d38-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d38-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d38-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5d38-118">See also</span></span>
- [<span data-ttu-id="e5d38-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5d38-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e5d38-120">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5d38-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
