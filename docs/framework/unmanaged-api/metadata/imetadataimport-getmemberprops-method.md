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
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177229"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="8d545-102">IMetaDataImport::GetMemberProps (Método)</span><span class="sxs-lookup"><span data-stu-id="8d545-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="8d545-103">Obtiene información almacenada en los metadatos de una definición de miembro especificada, incluido <xref:System.Type> el nombre, la firma binaria y la dirección virtual relativa, del miembro al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="8d545-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="8d545-104">Este es un método auxiliar simple: si *mb* es un MethodDef, a continuación, **GetMethodProps** se llama; si *mb* es un FieldDef, a continuación, **GetFieldProps** se llama.</span><span class="sxs-lookup"><span data-stu-id="8d545-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="8d545-105">Consulte estos otros métodos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d545-105">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8d545-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d545-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="8d545-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d545-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="8d545-108">[en] El token que hace referencia al miembro para el que se obtienen los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="8d545-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="8d545-109">[fuera] Puntero al token de metadatos que representa la clase del miembro.</span><span class="sxs-lookup"><span data-stu-id="8d545-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="8d545-110">[fuera] El nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="8d545-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="8d545-111">[en] El tamaño en caracteres anchos del `szMember` búfer.</span><span class="sxs-lookup"><span data-stu-id="8d545-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="8d545-112">[fuera] El tamaño en caracteres anchos del nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="8d545-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="8d545-113">[fuera] Cualquier valor de marca aplicado al miembro.</span><span class="sxs-lookup"><span data-stu-id="8d545-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="8d545-114">[fuera] Un puntero a la firma de metadatos binarios del miembro.</span><span class="sxs-lookup"><span data-stu-id="8d545-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="8d545-115">[fuera] El tamaño en `ppvSigBlob`bytes de .</span><span class="sxs-lookup"><span data-stu-id="8d545-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="8d545-116">[fuera] Un puntero a la dirección virtual relativa del miembro.</span><span class="sxs-lookup"><span data-stu-id="8d545-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="8d545-117">[fuera] Cualquier indicador de implementación de método asociado con el miembro.</span><span class="sxs-lookup"><span data-stu-id="8d545-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="8d545-118">[fuera] Una bandera que <xref:System.ValueType>marca un archivo .</span><span class="sxs-lookup"><span data-stu-id="8d545-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="8d545-119">Es uno de `ELEMENT_TYPE_*` los valores.</span><span class="sxs-lookup"><span data-stu-id="8d545-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="8d545-120">[fuera] Un valor de cadena constante devuelto por este miembro.</span><span class="sxs-lookup"><span data-stu-id="8d545-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="8d545-121">[fuera] El tamaño en `ppValue`caracteres `ppValue` de , o cero si no contiene una cadena.</span><span class="sxs-lookup"><span data-stu-id="8d545-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d545-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d545-122">Requirements</span></span>  
 <span data-ttu-id="8d545-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d545-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d545-124">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8d545-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d545-125">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d545-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8d545-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d545-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d545-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d545-127">See also</span></span>

- [<span data-ttu-id="8d545-128">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d545-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8d545-129">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d545-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
