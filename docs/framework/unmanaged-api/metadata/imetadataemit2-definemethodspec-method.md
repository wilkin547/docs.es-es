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
ms.openlocfilehash: a5d9342b8bfe650106ccf9daf2a91dfbcd575446
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175545"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="fa8d5-102">IMetaDataEmit2::DefineMethodSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="fa8d5-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="fa8d5-103">Crea una instancia genérica de un método y obtiene un token a la definición.</span><span class="sxs-lookup"><span data-stu-id="fa8d5-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa8d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa8d5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa8d5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa8d5-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="fa8d5-106">[en] Un token para el método para crear la instancia genérica.</span><span class="sxs-lookup"><span data-stu-id="fa8d5-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="fa8d5-107">El token debe `mdMethodDef` ser `mdMemberRef`de tipo o .</span><span class="sxs-lookup"><span data-stu-id="fa8d5-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="fa8d5-108">[en] Un puntero a la firma COM+ binaria del método.</span><span class="sxs-lookup"><span data-stu-id="fa8d5-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="fa8d5-109">[en] El tamaño, en `pvSigBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="fa8d5-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="fa8d5-110">[fuera] Un token para la definición de firma de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="fa8d5-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa8d5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa8d5-111">Requirements</span></span>  
 <span data-ttu-id="fa8d5-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa8d5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa8d5-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fa8d5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa8d5-114">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa8d5-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa8d5-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa8d5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8d5-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa8d5-116">See also</span></span>

- [<span data-ttu-id="fa8d5-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa8d5-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="fa8d5-118">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa8d5-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
