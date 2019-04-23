---
title: IMetaDataImport2::GetMethodSpecProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c35212e7d261a5b385823fdaa345f6fbd638571c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079349"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="363ee-102">IMetaDataImport2::GetMethodSpecProps (Método)</span><span class="sxs-lookup"><span data-stu-id="363ee-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="363ee-103">Obtiene la firma de metadatos del método al que hace referencia el MethodSpec especificado (token).</span><span class="sxs-lookup"><span data-stu-id="363ee-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="363ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="363ee-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="363ee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="363ee-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="363ee-106">[in] Un token MethodSpec que representa la instancia del método.</span><span class="sxs-lookup"><span data-stu-id="363ee-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="363ee-107">[out] Un puntero al token MethodDef o MethodRef que representa la definición del método.</span><span class="sxs-lookup"><span data-stu-id="363ee-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="363ee-108">[out] Un puntero a la firma de metadatos binaria del método.</span><span class="sxs-lookup"><span data-stu-id="363ee-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="363ee-109">[out] El tamaño, en bytes, de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="363ee-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="363ee-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="363ee-110">Requirements</span></span>  
 <span data-ttu-id="363ee-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="363ee-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="363ee-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="363ee-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="363ee-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="363ee-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="363ee-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="363ee-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="363ee-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="363ee-115">See also</span></span>

- [<span data-ttu-id="363ee-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="363ee-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="363ee-117">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="363ee-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
