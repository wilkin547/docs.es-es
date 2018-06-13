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
ms.openlocfilehash: 3249ad76c428752c91540e135bc978d3fe835de1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448138"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="78f86-102">IMetaDataImport2::GetMethodSpecProps (Método)</span><span class="sxs-lookup"><span data-stu-id="78f86-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="78f86-103">Obtiene la firma de metadatos del método al que hace referencia el MethodSpec especificado (token).</span><span class="sxs-lookup"><span data-stu-id="78f86-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78f86-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="78f86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78f86-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="78f86-106">[in] Símbolo (token) de MethodSpec que representa la creación de instancias del método.</span><span class="sxs-lookup"><span data-stu-id="78f86-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="78f86-107">[out] Un puntero al token MethodDef o MethodRef que representa la definición de método.</span><span class="sxs-lookup"><span data-stu-id="78f86-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="78f86-108">[out] Un puntero a la firma de metadatos binaria del método.</span><span class="sxs-lookup"><span data-stu-id="78f86-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="78f86-109">[out] El tamaño, en bytes, de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="78f86-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f86-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78f86-110">Requirements</span></span>  
 <span data-ttu-id="78f86-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78f86-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78f86-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="78f86-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78f86-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78f86-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78f86-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78f86-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f86-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="78f86-115">See Also</span></span>  
 [<span data-ttu-id="78f86-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="78f86-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="78f86-117">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="78f86-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
