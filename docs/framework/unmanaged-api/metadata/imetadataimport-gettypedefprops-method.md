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
ms.openlocfilehash: a482c7a06efe888408206f2de569e0a8739b85b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121516"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="cae11-102">IMetaDataImport::GetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="cae11-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="cae11-103">Devuelve información de metadatos para el <xref:System.Type> representado por el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="cae11-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae11-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cae11-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="cae11-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cae11-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="cae11-106">[in] El token de TypeDef que representa el tipo para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="cae11-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="cae11-107">[out] Un búfer que contiene el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="cae11-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="cae11-108">[in] El tamaño en caracteres anchos de `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="cae11-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="cae11-109">[out] El número de caracteres anchos que se devuelven en `szTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="cae11-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="cae11-110">[out] Un puntero a cualquier marcador que modifique la definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="cae11-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="cae11-111">Este valor es una máscara de bits desde el [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="cae11-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="cae11-112">[out] Un token de metadatos de TypeDef o TypeRef que representa el tipo base del tipo solicitado.</span><span class="sxs-lookup"><span data-stu-id="cae11-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cae11-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cae11-113">Requirements</span></span>  
 <span data-ttu-id="cae11-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cae11-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cae11-115">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="cae11-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cae11-116">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cae11-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="cae11-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cae11-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cae11-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cae11-118">See also</span></span>

- [<span data-ttu-id="cae11-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cae11-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cae11-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cae11-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
