---
description: 'Más información sobre: IMetaDataImport:: Getpropertyprops ((método)'
title: IMetaDataImport::GetPropertyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
ms.openlocfilehash: 25fae4488117a35d94479ce501154679b6b536ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789182"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="10ccf-103">IMetaDataImport::GetPropertyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="10ccf-103">IMetaDataImport::GetPropertyProps Method</span></span>

<span data-ttu-id="10ccf-104">Obtiene los metadatos de la propiedad representada por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="10ccf-104">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ccf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10ccf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,
   [out] LPCWSTR           szProperty,
   [in]  ULONG             cchProperty,
   [out] ULONG             *pchProperty,
   [out] DWORD             *pdwPropFlags,
   [out] PCCOR_SIGNATURE   *ppvSig,
   [out] ULONG             *pbSig,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,
   [out] mdMethodDef       *pmdGetter,
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,
   [out] ULONG             *pcOtherMethod
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10ccf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10ccf-106">Parameters</span></span>  

 `prop`  
 <span data-ttu-id="10ccf-107">de Token que representa la propiedad para la que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="10ccf-107">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="10ccf-108">enuncia Puntero al token de TypeDef que representa el tipo que implementa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="10ccf-108">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="10ccf-109">enuncia Búfer que contiene el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="10ccf-109">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="10ccf-110">de Tamaño en caracteres anchos de `szProperty` .</span><span class="sxs-lookup"><span data-stu-id="10ccf-110">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="10ccf-111">enuncia Número de caracteres anchos devueltos en `szProperty` .</span><span class="sxs-lookup"><span data-stu-id="10ccf-111">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="10ccf-112">enuncia Un puntero a cualquier marcador de atributo aplicado a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="10ccf-112">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="10ccf-113">Este valor es una máscara de máscara de la enumeración [CorPropertyAttr (](corpropertyattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="10ccf-113">This value is a bitmask from the [CorPropertyAttr](corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="10ccf-114">enuncia Puntero a la firma de metadatos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="10ccf-114">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="10ccf-115">enuncia Número de bytes devueltos en `ppvSig` .</span><span class="sxs-lookup"><span data-stu-id="10ccf-115">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="10ccf-116">enuncia Marca que especifica el tipo de la constante que es el valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="10ccf-116">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="10ccf-117">Este valor procede de la enumeración CorElementType.</span><span class="sxs-lookup"><span data-stu-id="10ccf-117">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="10ccf-118">enuncia Puntero a los bytes que almacenan el valor predeterminado de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="10ccf-118">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="10ccf-119">enuncia Tamaño en caracteres anchos de `ppDefaultValue` , si `pdwCPlusTypeFlag` es ELEMENT_TYPE_STRING; de lo contrario, este valor no es relevante.</span><span class="sxs-lookup"><span data-stu-id="10ccf-119">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="10ccf-120">En ese caso, la longitud de `ppDefaultValue` se deduce del tipo especificado por `pdwCPlusTypeFlag` .</span><span class="sxs-lookup"><span data-stu-id="10ccf-120">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="10ccf-121">enuncia Puntero al token de MethodDef que representa el método de descriptor de acceso set para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="10ccf-121">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="10ccf-122">enuncia Puntero al token de MethodDef que representa el método de descriptor de acceso get para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="10ccf-122">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="10ccf-123">enuncia Matriz de tokens de MethodDef que representan otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="10ccf-123">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="10ccf-124">[in] Tamaño máximo de la matriz `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="10ccf-124">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="10ccf-125">Si no proporciona una matriz lo suficientemente grande como para contener todos los métodos, se omiten sin ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="10ccf-125">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="10ccf-126">enuncia Número de tokens de MethodDef devueltos en `rmdOtherMethod` .</span><span class="sxs-lookup"><span data-stu-id="10ccf-126">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10ccf-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10ccf-127">Requirements</span></span>  

 <span data-ttu-id="10ccf-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10ccf-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ccf-129">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="10ccf-129">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10ccf-130">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10ccf-130">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10ccf-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10ccf-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ccf-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="10ccf-132">See also</span></span>

- [<span data-ttu-id="10ccf-133">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10ccf-133">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="10ccf-134">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10ccf-134">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
