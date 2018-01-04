---
title: "IMetaDataImport2::GetMethodSpecProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetMethodSpecProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6c0e079d32a39589b77e1361756c17bdc8867e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="a9eb4-102">IMetaDataImport2::GetMethodSpecProps (Método)</span><span class="sxs-lookup"><span data-stu-id="a9eb4-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="a9eb4-103">Obtiene la firma de metadatos del método al que hace referencia el MethodSpec especificado (token).</span><span class="sxs-lookup"><span data-stu-id="a9eb4-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9eb4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9eb4-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9eb4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9eb4-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="a9eb4-106">[in] Símbolo (token) de MethodSpec que representa la creación de instancias del método.</span><span class="sxs-lookup"><span data-stu-id="a9eb4-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="a9eb4-107">[out] Un puntero al token MethodDef o MethodRef que representa la definición de método.</span><span class="sxs-lookup"><span data-stu-id="a9eb4-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="a9eb4-108">[out] Un puntero a la firma de metadatos binaria del método.</span><span class="sxs-lookup"><span data-stu-id="a9eb4-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="a9eb4-109">[out] El tamaño, en bytes, de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="a9eb4-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9eb4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9eb4-110">Requirements</span></span>  
 <span data-ttu-id="a9eb4-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9eb4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9eb4-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9eb4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9eb4-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9eb4-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9eb4-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9eb4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9eb4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9eb4-115">See Also</span></span>  
 [<span data-ttu-id="a9eb4-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9eb4-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="a9eb4-117">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9eb4-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
