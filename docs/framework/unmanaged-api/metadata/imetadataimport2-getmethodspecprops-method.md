---
description: 'Más información sobre: IMetaDataImport2:: GetMethodSpecProps ((método)'
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
ms.openlocfilehash: 77f3f78905d1f7f44af0e9c7a75746b4e5b6e684
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688655"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="9360c-103">IMetaDataImport2::GetMethodSpecProps (Método)</span><span class="sxs-lookup"><span data-stu-id="9360c-103">IMetaDataImport2::GetMethodSpecProps Method</span></span>

<span data-ttu-id="9360c-104">Obtiene la firma de metadatos del método al que hace referencia el token MethodSpec especificado.</span><span class="sxs-lookup"><span data-stu-id="9360c-104">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9360c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9360c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,
   [out] ULONG            *pcbSigBlob  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="9360c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9360c-106">Parameters</span></span>  

 `mi`  
 <span data-ttu-id="9360c-107">de Símbolo (token) de MethodSpec que representa la creación de instancias del método.</span><span class="sxs-lookup"><span data-stu-id="9360c-107">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="9360c-108">enuncia Puntero al token MethodDef o MethodRef que representa la definición del método.</span><span class="sxs-lookup"><span data-stu-id="9360c-108">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="9360c-109">enuncia Puntero a la firma de metadatos binarios del método.</span><span class="sxs-lookup"><span data-stu-id="9360c-109">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="9360c-110">enuncia Tamaño, en bytes, de `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="9360c-110">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9360c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9360c-111">Requirements</span></span>  

 <span data-ttu-id="9360c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9360c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9360c-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9360c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9360c-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9360c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9360c-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9360c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9360c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9360c-116">See also</span></span>

- [<span data-ttu-id="9360c-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9360c-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="9360c-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9360c-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
