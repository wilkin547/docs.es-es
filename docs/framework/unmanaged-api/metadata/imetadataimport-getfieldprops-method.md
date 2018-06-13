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
ms.openlocfilehash: 04b6c04868efff31253b2d723c5783060382212b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448978"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="f507f-102">IMetaDataImport::GetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="f507f-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="f507f-103">Obtiene los metadatos asociados al campo al que hace referencia el token de FieldDef especificado.</span><span class="sxs-lookup"><span data-stu-id="f507f-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f507f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f507f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f507f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f507f-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="f507f-106">[in] Símbolo (token) de FieldDef que representa el campo para obtener los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="f507f-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="f507f-107">[out] Un puntero a un token de TypeDef que representa el tipo de la clase a la que pertenece el campo.</span><span class="sxs-lookup"><span data-stu-id="f507f-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="f507f-108">[out] El nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="f507f-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="f507f-109">[in] El tamaño en caracteres anchos del búfer de *szField*.</span><span class="sxs-lookup"><span data-stu-id="f507f-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="f507f-110">[out] El tamaño real del búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="f507f-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="f507f-111">[out] Marcas asociadas a los metadatos del campo.</span><span class="sxs-lookup"><span data-stu-id="f507f-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="f507f-112">[in] Un puntero al valor de metadatos binaria que describe el campo.</span><span class="sxs-lookup"><span data-stu-id="f507f-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="f507f-113">[out] El tamaño en bytes de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="f507f-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="f507f-114">[out] Una marca que especifica el tipo de valor del campo.</span><span class="sxs-lookup"><span data-stu-id="f507f-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f507f-115">[out] Un valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="f507f-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="f507f-116">[out] El tamaño en caracteres de `ppValue`, o cero si no existe ninguna cadena.</span><span class="sxs-lookup"><span data-stu-id="f507f-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f507f-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f507f-117">Requirements</span></span>  
 <span data-ttu-id="f507f-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f507f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f507f-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f507f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f507f-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f507f-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f507f-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f507f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f507f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f507f-122">See Also</span></span>  
 [<span data-ttu-id="f507f-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f507f-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f507f-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f507f-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
