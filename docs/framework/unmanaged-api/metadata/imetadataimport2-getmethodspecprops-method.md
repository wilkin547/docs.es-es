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
ms.openlocfilehash: 2eba599c0f7d47ab78c1b158129f03877a4a5d9f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702633"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="5dfc9-102">IMetaDataImport2::GetMethodSpecProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5dfc9-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>

<span data-ttu-id="5dfc9-103">Obtiene la firma de metadatos del método al que hace referencia el token MethodSpec especificado.</span><span class="sxs-lookup"><span data-stu-id="5dfc9-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dfc9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5dfc9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,
   [out] ULONG            *pcbSigBlob  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="5dfc9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5dfc9-105">Parameters</span></span>  

 `mi`  
 <span data-ttu-id="5dfc9-106">de Símbolo (token) de MethodSpec que representa la creación de instancias del método.</span><span class="sxs-lookup"><span data-stu-id="5dfc9-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="5dfc9-107">enuncia Puntero al token MethodDef o MethodRef que representa la definición del método.</span><span class="sxs-lookup"><span data-stu-id="5dfc9-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="5dfc9-108">enuncia Puntero a la firma de metadatos binarios del método.</span><span class="sxs-lookup"><span data-stu-id="5dfc9-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="5dfc9-109">enuncia Tamaño, en bytes, de `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="5dfc9-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dfc9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5dfc9-110">Requirements</span></span>  

 <span data-ttu-id="5dfc9-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dfc9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dfc9-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5dfc9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5dfc9-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5dfc9-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5dfc9-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dfc9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dfc9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5dfc9-115">See also</span></span>

- [<span data-ttu-id="5dfc9-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5dfc9-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="5dfc9-117">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5dfc9-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
