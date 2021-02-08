---
description: 'Más información sobre: IMetaDataImport:: Getfieldprops ((método)'
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
ms.openlocfilehash: 76735f837ff53b46b35cdf8c39990ed8689cc69c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789208"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="f3220-103">IMetaDataImport::GetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="f3220-103">IMetaDataImport::GetFieldProps Method</span></span>

<span data-ttu-id="f3220-104">Obtiene los metadatos asociados al campo al que hace referencia el token de FieldDef especificado.</span><span class="sxs-lookup"><span data-stu-id="f3220-104">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3220-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3220-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f3220-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3220-106">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="f3220-107">de Un token de FieldDef que representa el campo para el que se van a obtener los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="f3220-107">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="f3220-108">enuncia Un puntero a un token de TypeDef que representa el tipo de la clase a la que pertenece el campo.</span><span class="sxs-lookup"><span data-stu-id="f3220-108">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="f3220-109">enuncia Nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="f3220-109">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="f3220-110">de Tamaño en caracteres anchos del búfer para *szField*.</span><span class="sxs-lookup"><span data-stu-id="f3220-110">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="f3220-111">enuncia Tamaño real del búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="f3220-111">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="f3220-112">enuncia Marcas asociadas a los metadatos del campo.</span><span class="sxs-lookup"><span data-stu-id="f3220-112">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="f3220-113">de Puntero al valor de metadatos binarios que describe el campo.</span><span class="sxs-lookup"><span data-stu-id="f3220-113">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="f3220-114">enuncia Tamaño en bytes de `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="f3220-114">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="f3220-115">enuncia Marca que especifica el tipo de valor del campo.</span><span class="sxs-lookup"><span data-stu-id="f3220-115">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f3220-116">enuncia Valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="f3220-116">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="f3220-117">enuncia Tamaño en caracteres de `ppValue` , o cero si no existe ninguna cadena.</span><span class="sxs-lookup"><span data-stu-id="f3220-117">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3220-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3220-118">Requirements</span></span>  

 <span data-ttu-id="f3220-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3220-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3220-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f3220-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3220-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3220-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3220-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3220-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3220-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3220-123">See also</span></span>

- [<span data-ttu-id="f3220-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3220-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f3220-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3220-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
