---
title: IMetaDataImport::GetMemberRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2c431abb7a4a872454b9c2689ee195ed36ef236
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177019"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="7b310-102">IMetaDataImport::GetMemberRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7b310-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="7b310-103">Obtiene los metadatos asociados al miembro al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="7b310-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b310-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b310-104">Syntax</span></span>  
  
```  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b310-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b310-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="7b310-106">[in] El token MemberRef para devolver los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="7b310-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="7b310-107">[out] Un token de TypeDef o TypeRef o TypeSpec que representa la clase que declara el miembro o un token ModuleRef que representa la clase de módulo que declara el miembro o MethodDef que representa al miembro.</span><span class="sxs-lookup"><span data-stu-id="7b310-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="7b310-108">[out] Un búfer de cadena para el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="7b310-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="7b310-109">[in] El tamaño solicitado en caracteres anchos de `szMember`.</span><span class="sxs-lookup"><span data-stu-id="7b310-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="7b310-110">[out] El tamaño devuelto en caracteres anchos de `szMember`.</span><span class="sxs-lookup"><span data-stu-id="7b310-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="7b310-111">[out] Un puntero a la firma de metadatos binaria para el miembro.</span><span class="sxs-lookup"><span data-stu-id="7b310-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="7b310-112">[out] El tamaño en bytes de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="7b310-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b310-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b310-113">Requirements</span></span>  
 <span data-ttu-id="7b310-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b310-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b310-115">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b310-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b310-116">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b310-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7b310-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7b310-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b310-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b310-118">See also</span></span>

- [<span data-ttu-id="7b310-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b310-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7b310-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b310-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
