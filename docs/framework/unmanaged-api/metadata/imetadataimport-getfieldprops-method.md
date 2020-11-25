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
ms.openlocfilehash: 458a90bc47711d9f831805faa8468a49f3e0d305
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704008"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="120e7-102">IMetaDataImport::GetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="120e7-102">IMetaDataImport::GetFieldProps Method</span></span>

<span data-ttu-id="120e7-103">Obtiene los metadatos asociados al campo al que hace referencia el token de FieldDef especificado.</span><span class="sxs-lookup"><span data-stu-id="120e7-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="120e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="120e7-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="120e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="120e7-105">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="120e7-106">de Un token de FieldDef que representa el campo para el que se van a obtener los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="120e7-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="120e7-107">enuncia Un puntero a un token de TypeDef que representa el tipo de la clase a la que pertenece el campo.</span><span class="sxs-lookup"><span data-stu-id="120e7-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="120e7-108">enuncia Nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="120e7-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="120e7-109">de Tamaño en caracteres anchos del búfer para *szField*.</span><span class="sxs-lookup"><span data-stu-id="120e7-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="120e7-110">enuncia Tamaño real del búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="120e7-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="120e7-111">enuncia Marcas asociadas a los metadatos del campo.</span><span class="sxs-lookup"><span data-stu-id="120e7-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="120e7-112">de Puntero al valor de metadatos binarios que describe el campo.</span><span class="sxs-lookup"><span data-stu-id="120e7-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="120e7-113">enuncia Tamaño en bytes de `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="120e7-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="120e7-114">enuncia Marca que especifica el tipo de valor del campo.</span><span class="sxs-lookup"><span data-stu-id="120e7-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="120e7-115">enuncia Valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="120e7-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="120e7-116">enuncia Tamaño en caracteres de `ppValue` , o cero si no existe ninguna cadena.</span><span class="sxs-lookup"><span data-stu-id="120e7-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="120e7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="120e7-117">Requirements</span></span>  

 <span data-ttu-id="120e7-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="120e7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="120e7-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="120e7-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="120e7-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="120e7-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="120e7-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="120e7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120e7-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="120e7-122">See also</span></span>

- [<span data-ttu-id="120e7-123">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="120e7-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="120e7-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="120e7-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
