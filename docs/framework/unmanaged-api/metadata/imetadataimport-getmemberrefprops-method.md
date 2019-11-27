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
ms.openlocfilehash: 1d6d66ea62cbf679f722f830b3638455001aedd6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437490"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="7f862-102">IMetaDataImport::GetMemberRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7f862-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="7f862-103">Obtiene los metadatos asociados al miembro al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="7f862-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f862-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f862-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="7f862-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7f862-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="7f862-106">de Token de MemberRef para el que se van a devolver los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="7f862-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="7f862-107">enuncia Un token TypeDef o TypeRef, o TypeSpec que representa la clase que declara el miembro, o un token ModuleRef que representa la clase de módulo que declara el miembro, o un MethodDef que representa el miembro.</span><span class="sxs-lookup"><span data-stu-id="7f862-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="7f862-108">enuncia Un búfer de cadena para el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="7f862-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="7f862-109">de Tamaño solicitado en caracteres anchos de `szMember`.</span><span class="sxs-lookup"><span data-stu-id="7f862-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="7f862-110">enuncia Tamaño devuelto en caracteres anchos de `szMember`.</span><span class="sxs-lookup"><span data-stu-id="7f862-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="7f862-111">enuncia Puntero a la firma de metadatos binarios para el miembro.</span><span class="sxs-lookup"><span data-stu-id="7f862-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="7f862-112">enuncia Tamaño en bytes de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="7f862-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f862-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f862-113">Requirements</span></span>  
 <span data-ttu-id="7f862-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f862-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f862-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7f862-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f862-116">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7f862-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f862-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f862-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f862-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f862-118">See also</span></span>

- [<span data-ttu-id="7f862-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f862-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7f862-120">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f862-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
