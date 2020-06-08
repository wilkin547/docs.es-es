---
title: IMetaDataImport::GetCustomAttributeProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
ms.openlocfilehash: 320cfae93f8aae94f9315e8e20ed6cf7f9cced7c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491321"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="0c934-102">IMetaDataImport::GetCustomAttributeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="0c934-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="0c934-103">Obtiene el valor del atributo personalizado a partir de su token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="0c934-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c934-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c934-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c934-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c934-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="0c934-106">[in] Token de metadatos que representa el atributo personalizado que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="0c934-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="0c934-107">[out, optional] Token de metadatos que representa el objeto que es modificado por el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="0c934-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="0c934-108">Este valor puede ser cualquier tipo de token de metadatos, excepto `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="0c934-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="0c934-109">[out, optional] Token de metadatos `mdMethodDef` o `mdMemberRef` que representa el objeto <xref:System.Type> del atributo personalizado devuelto.</span><span class="sxs-lookup"><span data-stu-id="0c934-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="0c934-110">[out, optional] Puntero a una matriz de datos que es el valor del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="0c934-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="0c934-111">[out, optional] Tamaño en bytes de los datos devueltos en \*`ppBlob`.</span><span class="sxs-lookup"><span data-stu-id="0c934-111">[out, optional] The size in bytes of the data returned in \*`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c934-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c934-112">Remarks</span></span>  
 <span data-ttu-id="0c934-113">Un atributo personalizado se almacena como una matriz de datos, que es el formato que reconoce el motor de metadatos.</span><span class="sxs-lookup"><span data-stu-id="0c934-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c934-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c934-114">Requirements</span></span>  
 <span data-ttu-id="0c934-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c934-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c934-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0c934-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c934-117">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0c934-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c934-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c934-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c934-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0c934-119">See also</span></span>

- [<span data-ttu-id="0c934-120">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c934-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0c934-121">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c934-121">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
