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
ms.openlocfilehash: 0bfbfec930c193ea05a01bd5bd9f46d2ec6714b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175296"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="7a81c-102">IMetaDataImport2::GetMethodSpecProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7a81c-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="7a81c-103">Obtiene la firma de metadatos del método al que hace referencia el token MethodSpec especificado.</span><span class="sxs-lookup"><span data-stu-id="7a81c-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a81c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a81c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,
   [out] ULONG            *pcbSigBlob  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="7a81c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7a81c-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="7a81c-106">[en] Un token MethodSpec que representa la creación de instancias del método.</span><span class="sxs-lookup"><span data-stu-id="7a81c-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="7a81c-107">[fuera] Puntero al token MethodDef o MethodRef que representa la definición del método.</span><span class="sxs-lookup"><span data-stu-id="7a81c-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="7a81c-108">[fuera] Un puntero a la firma de metadatos binarios del método.</span><span class="sxs-lookup"><span data-stu-id="7a81c-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="7a81c-109">[fuera] El tamaño, en `ppvSigBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="7a81c-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a81c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a81c-110">Requirements</span></span>  
 <span data-ttu-id="7a81c-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a81c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a81c-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7a81c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a81c-113">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a81c-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a81c-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a81c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a81c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a81c-115">See also</span></span>

- [<span data-ttu-id="7a81c-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7a81c-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="7a81c-117">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7a81c-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
