---
title: IMetaDataImport::GetMemberProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98d7be5adc81cff09b121265e7d5b5f712122607
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611415"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="82cda-102">IMetaDataImport::GetMemberProps (Método)</span><span class="sxs-lookup"><span data-stu-id="82cda-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="82cda-103">Obtiene información de metadatos, incluidos el nombre, la firma binaria y la dirección virtual relativa, de la <xref:System.Type> miembro al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="82cda-103">Gets metadata information, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82cda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82cda-104">Syntax</span></span>  
  
```  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82cda-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82cda-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="82cda-106">[in] El token que hace referencia al miembro para obtener los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="82cda-106">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="82cda-107">[out] Un puntero al token de metadatos que representa la clase del miembro.</span><span class="sxs-lookup"><span data-stu-id="82cda-107">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="82cda-108">[out] El nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="82cda-108">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="82cda-109">[in] El tamaño en caracteres anchos de la `szMember` búfer.</span><span class="sxs-lookup"><span data-stu-id="82cda-109">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="82cda-110">[out] El tamaño en caracteres anchos del nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="82cda-110">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="82cda-111">[out] Los valores de marca aplicados al miembro.</span><span class="sxs-lookup"><span data-stu-id="82cda-111">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="82cda-112">[out] Un puntero a la firma de metadatos binaria del miembro.</span><span class="sxs-lookup"><span data-stu-id="82cda-112">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="82cda-113">[out] El tamaño en bytes de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="82cda-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="82cda-114">[out] Un puntero a la dirección virtual relativa del miembro.</span><span class="sxs-lookup"><span data-stu-id="82cda-114">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="82cda-115">[out] Los marcadores de implementación de método asociados al miembro.</span><span class="sxs-lookup"><span data-stu-id="82cda-115">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="82cda-116">[out] Una marca que marca un <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="82cda-116">[out] A flag that marks a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="82cda-117">[out] Un valor de cadena constante devuelto por este miembro.</span><span class="sxs-lookup"><span data-stu-id="82cda-117">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="82cda-118">[out] El tamaño en caracteres de `ppValue`, o cero si `ppValue` no contiene una cadena.</span><span class="sxs-lookup"><span data-stu-id="82cda-118">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82cda-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82cda-119">Requirements</span></span>  
 <span data-ttu-id="82cda-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82cda-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82cda-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="82cda-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82cda-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82cda-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82cda-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82cda-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82cda-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="82cda-124">See also</span></span>
- [<span data-ttu-id="82cda-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82cda-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="82cda-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82cda-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
