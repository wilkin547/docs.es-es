---
title: IMetaDataImport::GetFieldProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc4e8140485902e4677bca0228bc125c64b497f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671868"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="47fd2-102">IMetaDataImport::GetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="47fd2-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="47fd2-103">Obtiene los metadatos asociados al campo al que hace referencia el token de FieldDef especificado.</span><span class="sxs-lookup"><span data-stu-id="47fd2-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47fd2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47fd2-104">Syntax</span></span>  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47fd2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47fd2-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="47fd2-106">[in] Un token de FieldDef que representa el campo para obtener los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="47fd2-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="47fd2-107">[out] Un puntero a un token de TypeDef que representa el tipo de la clase a la que pertenece el campo.</span><span class="sxs-lookup"><span data-stu-id="47fd2-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="47fd2-108">[out] El nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="47fd2-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="47fd2-109">[in] El tamaño en caracteres anchos del búfer para *szField*.</span><span class="sxs-lookup"><span data-stu-id="47fd2-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="47fd2-110">[out] El tamaño real del búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="47fd2-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="47fd2-111">[out] Marcas asociadas a los metadatos del campo.</span><span class="sxs-lookup"><span data-stu-id="47fd2-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="47fd2-112">[in] Un puntero al valor binario de metadatos que describe el campo.</span><span class="sxs-lookup"><span data-stu-id="47fd2-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="47fd2-113">[out] El tamaño en bytes de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="47fd2-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="47fd2-114">[out] Una marca que especifica el tipo de valor del campo.</span><span class="sxs-lookup"><span data-stu-id="47fd2-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="47fd2-115">[out] Un valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="47fd2-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="47fd2-116">[out] El tamaño en caracteres de `ppValue`, o cero si no existe ninguna cadena.</span><span class="sxs-lookup"><span data-stu-id="47fd2-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47fd2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47fd2-117">Requirements</span></span>  
 <span data-ttu-id="47fd2-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47fd2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47fd2-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="47fd2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47fd2-120">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47fd2-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47fd2-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47fd2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fd2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="47fd2-122">See also</span></span>
- [<span data-ttu-id="47fd2-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47fd2-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="47fd2-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47fd2-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
