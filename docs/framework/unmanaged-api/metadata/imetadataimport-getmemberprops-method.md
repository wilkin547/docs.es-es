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
ms.openlocfilehash: 83dec9b6ed3b1e538e0f1b7d13a33b8bdbc1cf54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200810"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="fc4c4-102">IMetaDataImport::GetMemberProps (Método)</span><span class="sxs-lookup"><span data-stu-id="fc4c4-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="fc4c4-103">Obtiene la información almacenada en los metadatos de una definición de miembro especificado, incluido el nombre, la firma binaria y la dirección virtual relativa, de la <xref:System.Type> miembro al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="fc4c4-104">Se trata de un método auxiliar simple: si *mb* es MethodDef, a continuación, **GetMethodProps** se denomina; si *mb* es un FieldDef, a continuación, **GetFieldProps** se llama.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="fc4c4-105">Consulte estos otros métodos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="fc4c4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc4c4-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fc4c4-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc4c4-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="fc4c4-108">[in] El token que hace referencia al miembro para obtener los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="fc4c4-109">[out] Un puntero al token de metadatos que representa la clase del miembro.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="fc4c4-110">[out] El nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="fc4c4-111">[in] El tamaño en caracteres anchos de la `szMember` búfer.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="fc4c4-112">[out] El tamaño en caracteres anchos del nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="fc4c4-113">[out] Los valores de marca aplicados al miembro.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="fc4c4-114">[out] Un puntero a la firma de metadatos binaria del miembro.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="fc4c4-115">[out] El tamaño en bytes de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="fc4c4-116">[out] Un puntero a la dirección virtual relativa del miembro.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="fc4c4-117">[out] Los marcadores de implementación de método asociados al miembro.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="fc4c4-118">[out] Una marca que marca un <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="fc4c4-119">Es uno de los `ELEMENT_TYPE_*` valores.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="fc4c4-120">[out] Un valor de cadena constante devuelto por este miembro.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="fc4c4-121">[out] El tamaño en caracteres de `ppValue`, o cero si `ppValue` no contiene una cadena.</span><span class="sxs-lookup"><span data-stu-id="fc4c4-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc4c4-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc4c4-122">Requirements</span></span>  
 <span data-ttu-id="fc4c4-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc4c4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc4c4-124">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="fc4c4-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc4c4-125">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc4c4-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fc4c4-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc4c4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc4c4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc4c4-127">See also</span></span>

- [<span data-ttu-id="fc4c4-128">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc4c4-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fc4c4-129">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc4c4-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
