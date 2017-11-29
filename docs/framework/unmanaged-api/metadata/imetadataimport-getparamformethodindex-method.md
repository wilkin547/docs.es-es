---
title: "IMetaDataImport::GetParamForMethodIndex (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetParamForMethodIndex
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cda4ffde7d38d74ddf7a81b6f0af4a556693094d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="74271-102">IMetaDataImport::GetParamForMethodIndex (Método)</span><span class="sxs-lookup"><span data-stu-id="74271-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="74271-103">Obtiene el token que representa un parámetro especificado del método representado por el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="74271-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74271-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74271-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74271-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74271-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="74271-106">[in] Un token que representa el método para devolver el token de parámetro.</span><span class="sxs-lookup"><span data-stu-id="74271-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="74271-107">[in] La posición ordinal en la lista de parámetros donde aparece el parámetro solicitado.</span><span class="sxs-lookup"><span data-stu-id="74271-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="74271-108">Parámetros se numeran a partir de uno, con el valor devuelto del método en la posición cero.</span><span class="sxs-lookup"><span data-stu-id="74271-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="74271-109">[out] Un puntero a un símbolo (token) de ParamDef que representa el parámetro solicitado.</span><span class="sxs-lookup"><span data-stu-id="74271-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74271-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74271-110">Requirements</span></span>  
 <span data-ttu-id="74271-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74271-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74271-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="74271-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74271-113">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74271-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74271-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74271-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74271-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="74271-115">See Also</span></span>  
 [<span data-ttu-id="74271-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74271-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="74271-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74271-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
