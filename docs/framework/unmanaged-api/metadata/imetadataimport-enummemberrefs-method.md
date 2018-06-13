---
title: IMetaDataImport::EnumMemberRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c148ee0b2c96f2a387dac54eaff690ab3f05ebf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447063"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="f695e-102">IMetaDataImport::EnumMemberRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="f695e-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="f695e-103">Enumera los tokens de MemberRef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="f695e-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f695e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f695e-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f695e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f695e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f695e-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="f695e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="f695e-107">[in] Símbolo (token) de TypeDef, TypeRef, MethodDef o ModuleRef para el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="f695e-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="f695e-108">[out] La matriz que se utiliza para almacenar los tokens de MemberRef.</span><span class="sxs-lookup"><span data-stu-id="f695e-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f695e-109">[in] Tamaño máximo de la matriz `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="f695e-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f695e-110">[out] El número real de símbolos (tokens) de MemberRef devueltos en `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="f695e-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f695e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f695e-111">Return Value</span></span>  
  
|<span data-ttu-id="f695e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f695e-112">HRESULT</span></span>|<span data-ttu-id="f695e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f695e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f695e-114">`EnumMemberRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f695e-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f695e-115">No hay ningún tokens de MemberRef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="f695e-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="f695e-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="f695e-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f695e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f695e-117">Requirements</span></span>  
 <span data-ttu-id="f695e-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f695e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f695e-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f695e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f695e-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f695e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f695e-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f695e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f695e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f695e-122">See Also</span></span>  
 [<span data-ttu-id="f695e-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f695e-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f695e-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f695e-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
