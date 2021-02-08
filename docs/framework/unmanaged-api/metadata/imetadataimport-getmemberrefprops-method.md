---
description: 'Más información sobre: IMetaDataImport:: Getmemberrefprops ((método)'
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
ms.openlocfilehash: b441f39d95c9af1e18d34a1a4d86d6cea33508c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783888"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="760d2-103">IMetaDataImport::GetMemberRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="760d2-103">IMetaDataImport::GetMemberRefProps Method</span></span>

<span data-ttu-id="760d2-104">Obtiene los metadatos asociados al miembro al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="760d2-104">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="760d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="760d2-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="760d2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="760d2-106">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="760d2-107">de Token de MemberRef para el que se van a devolver los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="760d2-107">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="760d2-108">enuncia Un token TypeDef o TypeRef, o TypeSpec que representa la clase que declara el miembro, o un token ModuleRef que representa la clase de módulo que declara el miembro, o un MethodDef que representa el miembro.</span><span class="sxs-lookup"><span data-stu-id="760d2-108">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="760d2-109">enuncia Un búfer de cadena para el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="760d2-109">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="760d2-110">de Tamaño solicitado en caracteres anchos de `szMember` .</span><span class="sxs-lookup"><span data-stu-id="760d2-110">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="760d2-111">enuncia Tamaño devuelto en caracteres anchos de `szMember` .</span><span class="sxs-lookup"><span data-stu-id="760d2-111">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="760d2-112">enuncia Puntero a la firma de metadatos binarios para el miembro.</span><span class="sxs-lookup"><span data-stu-id="760d2-112">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="760d2-113">enuncia Tamaño en bytes de `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="760d2-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="760d2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="760d2-114">Requirements</span></span>  

 <span data-ttu-id="760d2-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="760d2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="760d2-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="760d2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="760d2-117">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="760d2-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="760d2-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="760d2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760d2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="760d2-119">See also</span></span>

- [<span data-ttu-id="760d2-120">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="760d2-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="760d2-121">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="760d2-121">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
