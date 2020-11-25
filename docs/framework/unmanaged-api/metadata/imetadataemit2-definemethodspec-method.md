---
title: IMetaDataEmit2::DefineMethodSpec (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: 817b3a18b047bfca1f3a7c7099920a12e6253f58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712838"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="5853b-102">IMetaDataEmit2::DefineMethodSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="5853b-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>

<span data-ttu-id="5853b-103">Crea una instancia genérica de un método y obtiene un token para la definición.</span><span class="sxs-lookup"><span data-stu-id="5853b-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5853b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5853b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5853b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5853b-105">Parameters</span></span>  

 `tkParent`  
 <span data-ttu-id="5853b-106">de Token para el método del que se va a crear la instancia genérica.</span><span class="sxs-lookup"><span data-stu-id="5853b-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="5853b-107">El token debe ser de tipo `mdMethodDef` o `mdMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="5853b-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5853b-108">de Puntero a la firma COM+ binaria del método.</span><span class="sxs-lookup"><span data-stu-id="5853b-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="5853b-109">de Tamaño, en bytes, de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="5853b-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="5853b-110">enuncia Token para la definición de la firma de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="5853b-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5853b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5853b-111">Requirements</span></span>  

 <span data-ttu-id="5853b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5853b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5853b-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5853b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5853b-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5853b-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5853b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5853b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5853b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5853b-116">See also</span></span>

- [<span data-ttu-id="5853b-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5853b-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="5853b-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5853b-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
