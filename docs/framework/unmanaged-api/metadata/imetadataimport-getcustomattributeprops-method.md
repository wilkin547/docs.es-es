---
title: IMetaDataImport::GetCustomAttributeProps (Método)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
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
caps.latest.revision: 14
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1e6ef9443b99b3e6b36154558ce226d421dbc0a
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/10/2018
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="8ec70-102">IMetaDataImport::GetCustomAttributeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="8ec70-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="8ec70-103">Obtiene el valor del atributo personalizado a partir de su token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="8ec70-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ec70-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ec70-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8ec70-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="8ec70-106">[in] Token de metadatos que representa el atributo personalizado que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="8ec70-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="8ec70-107">[out, optional] Token de metadatos que representa el objeto que es modificado por el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="8ec70-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="8ec70-108">Este valor puede ser cualquier tipo de token de metadatos, excepto `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="8ec70-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="8ec70-109">[out, optional] Token de metadatos `mdMethodDef` o `mdMemberRef` que representa el objeto <xref:System.Type> del atributo personalizado devuelto.</span><span class="sxs-lookup"><span data-stu-id="8ec70-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="8ec70-110">[out, optional] Puntero a una matriz de datos que es el valor del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="8ec70-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="8ec70-111">[out, optional] Tamaño en bytes de los datos devueltos en \*`ppBlob`.</span><span class="sxs-lookup"><span data-stu-id="8ec70-111">[out, optional] The size in bytes of the data returned in \*`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ec70-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ec70-112">Remarks</span></span>  
 <span data-ttu-id="8ec70-113">Un atributo personalizado se almacena como una matriz de datos, que es el formato que reconoce el motor de metadatos.</span><span class="sxs-lookup"><span data-stu-id="8ec70-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ec70-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ec70-114">Requirements</span></span>  
 <span data-ttu-id="8ec70-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ec70-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ec70-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ec70-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ec70-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ec70-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ec70-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ec70-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec70-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ec70-119">See Also</span></span>  
 [<span data-ttu-id="8ec70-120">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ec70-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="8ec70-121">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ec70-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
