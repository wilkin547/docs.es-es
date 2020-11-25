---
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
ms.openlocfilehash: a16621f4c9b06f049239dc4e2335d70a167dd756
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729270"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="57d3c-102">IMetaDataImport::GetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="57d3c-102">IMetaDataImport::GetParamProps Method</span></span>

<span data-ttu-id="57d3c-103">Obtiene los valores de los metadatos del parámetro al que hace referencia el token de ParamDef especificado.</span><span class="sxs-lookup"><span data-stu-id="57d3c-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57d3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57d3c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="57d3c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57d3c-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="57d3c-106">de Un token ParamDef que representa el parámetro para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="57d3c-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="57d3c-107">enuncia Un puntero a un token MethodDef que representa el método que toma el parámetro.</span><span class="sxs-lookup"><span data-stu-id="57d3c-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="57d3c-108">enuncia Posición ordinal del parámetro en la lista de argumentos del método.</span><span class="sxs-lookup"><span data-stu-id="57d3c-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="57d3c-109">enuncia Búfer que contiene el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="57d3c-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="57d3c-110">de Tamaño solicitado en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="57d3c-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="57d3c-111">enuncia Tamaño devuelto en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="57d3c-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="57d3c-112">enuncia Un puntero a cualquier marcador de atributo asociado al parámetro.</span><span class="sxs-lookup"><span data-stu-id="57d3c-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="57d3c-113">Se trata de una máscara de máscara de `CorParamAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="57d3c-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="57d3c-114">enuncia Un puntero a una marca que especifica que el parámetro es un <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="57d3c-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="57d3c-115">enuncia Puntero a una cadena constante devuelta por el parámetro.</span><span class="sxs-lookup"><span data-stu-id="57d3c-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="57d3c-116">enuncia Tamaño de `ppValue` en caracteres anchos o cero si `ppValue` no contiene una cadena.</span><span class="sxs-lookup"><span data-stu-id="57d3c-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57d3c-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57d3c-117">Remarks</span></span>

<span data-ttu-id="57d3c-118">Los valores de secuencia de `pulSequence` comienzan por 1 para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="57d3c-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="57d3c-119">Un valor devuelto tiene un número de secuencia de 0.</span><span class="sxs-lookup"><span data-stu-id="57d3c-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="57d3c-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57d3c-120">Requirements</span></span>  

 <span data-ttu-id="57d3c-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57d3c-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57d3c-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="57d3c-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57d3c-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57d3c-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="57d3c-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57d3c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d3c-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57d3c-125">See also</span></span>

- [<span data-ttu-id="57d3c-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57d3c-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="57d3c-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57d3c-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
