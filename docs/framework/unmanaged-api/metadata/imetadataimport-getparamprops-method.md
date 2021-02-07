---
description: 'Más información sobre: IMetaDataImport:: Getparamprops ((método)'
title: IMetaDataImport::GetParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
ms.openlocfilehash: 2c48215836dfb3ae44edc9a2bf10d4028fd82bb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728124"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="95da7-103">IMetaDataImport::GetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="95da7-103">IMetaDataImport::GetParamProps Method</span></span>

<span data-ttu-id="95da7-104">Obtiene los valores de los metadatos del parámetro al que hace referencia el token de ParamDef especificado.</span><span class="sxs-lookup"><span data-stu-id="95da7-104">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95da7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95da7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95da7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="95da7-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="95da7-107">de Un token ParamDef que representa el parámetro para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="95da7-107">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="95da7-108">enuncia Un puntero a un token MethodDef que representa el método que toma el parámetro.</span><span class="sxs-lookup"><span data-stu-id="95da7-108">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="95da7-109">enuncia Posición ordinal del parámetro en la lista de argumentos del método.</span><span class="sxs-lookup"><span data-stu-id="95da7-109">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="95da7-110">enuncia Búfer que contiene el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="95da7-110">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="95da7-111">de Tamaño solicitado en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="95da7-111">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="95da7-112">enuncia Tamaño devuelto en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="95da7-112">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="95da7-113">enuncia Un puntero a cualquier marcador de atributo asociado al parámetro.</span><span class="sxs-lookup"><span data-stu-id="95da7-113">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="95da7-114">Se trata de una máscara de máscara de `CorParamAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="95da7-114">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="95da7-115">enuncia Un puntero a una marca que especifica que el parámetro es un <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="95da7-115">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="95da7-116">enuncia Puntero a una cadena constante devuelta por el parámetro.</span><span class="sxs-lookup"><span data-stu-id="95da7-116">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="95da7-117">enuncia Tamaño de `ppValue` en caracteres anchos o cero si `ppValue` no contiene una cadena.</span><span class="sxs-lookup"><span data-stu-id="95da7-117">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95da7-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="95da7-118">Remarks</span></span>

<span data-ttu-id="95da7-119">Los valores de secuencia de `pulSequence` comienzan por 1 para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="95da7-119">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="95da7-120">Un valor devuelto tiene un número de secuencia de 0.</span><span class="sxs-lookup"><span data-stu-id="95da7-120">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="95da7-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95da7-121">Requirements</span></span>  

 <span data-ttu-id="95da7-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95da7-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95da7-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="95da7-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95da7-124">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95da7-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95da7-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95da7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95da7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="95da7-126">See also</span></span>

- [<span data-ttu-id="95da7-127">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95da7-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="95da7-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95da7-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
