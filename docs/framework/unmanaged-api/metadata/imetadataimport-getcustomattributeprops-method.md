---
description: 'Más información sobre: IMetaDataImport:: Getcustomattributeprops ((método)'
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
ms.openlocfilehash: 9bd8e83301252d7ead225146e562d3a58feb244a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745390"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="3a1fa-103">IMetaDataImport::GetCustomAttributeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="3a1fa-103">IMetaDataImport::GetCustomAttributeProps Method</span></span>

<span data-ttu-id="3a1fa-104">Obtiene el valor del atributo personalizado a partir de su token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3a1fa-104">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a1fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a1fa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a1fa-106">Parameters</span></span>  

 `cv`  
 <span data-ttu-id="3a1fa-107">[in] Token de metadatos que representa el atributo personalizado que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="3a1fa-107">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="3a1fa-108">[out, optional] Token de metadatos que representa el objeto que es modificado por el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a1fa-108">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="3a1fa-109">Este valor puede ser cualquier tipo de token de metadatos, excepto `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="3a1fa-109">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="3a1fa-110">[out, optional] Token de metadatos `mdMethodDef` o `mdMemberRef` que representa el objeto <xref:System.Type> del atributo personalizado devuelto.</span><span class="sxs-lookup"><span data-stu-id="3a1fa-110">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="3a1fa-111">[out, optional] Puntero a una matriz de datos que es el valor del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a1fa-111">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="3a1fa-112">[out, optional] Tamaño en bytes de los datos devueltos en \*`ppBlob`.</span><span class="sxs-lookup"><span data-stu-id="3a1fa-112">[out, optional] The size in bytes of the data returned in \*`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a1fa-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3a1fa-113">Remarks</span></span>  

 <span data-ttu-id="3a1fa-114">Un atributo personalizado se almacena como una matriz de datos, que es el formato que reconoce el motor de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3a1fa-114">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a1fa-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a1fa-115">Requirements</span></span>  

 <span data-ttu-id="3a1fa-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a1fa-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a1fa-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3a1fa-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a1fa-118">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a1fa-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a1fa-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a1fa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1fa-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a1fa-120">See also</span></span>

- [<span data-ttu-id="3a1fa-121">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a1fa-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3a1fa-122">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a1fa-122">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
