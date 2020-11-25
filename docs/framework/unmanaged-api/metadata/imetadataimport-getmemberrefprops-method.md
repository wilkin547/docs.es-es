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
ms.openlocfilehash: 3237b67f8f711e9ef213d6fc66f1513c534fbdeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733209"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="d5455-102">IMetaDataImport::GetMemberRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="d5455-102">IMetaDataImport::GetMemberRefProps Method</span></span>

<span data-ttu-id="d5455-103">Obtiene los metadatos asociados al miembro al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="d5455-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5455-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5455-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d5455-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5455-105">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="d5455-106">de Token de MemberRef para el que se van a devolver los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="d5455-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="d5455-107">enuncia Un token TypeDef o TypeRef, o TypeSpec que representa la clase que declara el miembro, o un token ModuleRef que representa la clase de módulo que declara el miembro, o un MethodDef que representa el miembro.</span><span class="sxs-lookup"><span data-stu-id="d5455-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="d5455-108">enuncia Un búfer de cadena para el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="d5455-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="d5455-109">de Tamaño solicitado en caracteres anchos de `szMember` .</span><span class="sxs-lookup"><span data-stu-id="d5455-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="d5455-110">enuncia Tamaño devuelto en caracteres anchos de `szMember` .</span><span class="sxs-lookup"><span data-stu-id="d5455-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="d5455-111">enuncia Puntero a la firma de metadatos binarios para el miembro.</span><span class="sxs-lookup"><span data-stu-id="d5455-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="d5455-112">enuncia Tamaño en bytes de `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="d5455-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5455-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5455-113">Requirements</span></span>  

 <span data-ttu-id="d5455-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5455-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5455-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d5455-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5455-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5455-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5455-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5455-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5455-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5455-118">See also</span></span>

- [<span data-ttu-id="d5455-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5455-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d5455-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5455-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
