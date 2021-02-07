---
description: 'Más información acerca de: IMetaDataEmit2::D efineMethodSpec (método)'
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
ms.openlocfilehash: 4b5283375ba194a86a83b142b3b2bdc06bfd35da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745741"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="012df-103">IMetaDataEmit2::DefineMethodSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="012df-103">IMetaDataEmit2::DefineMethodSpec Method</span></span>

<span data-ttu-id="012df-104">Crea una instancia genérica de un método y obtiene un token para la definición.</span><span class="sxs-lookup"><span data-stu-id="012df-104">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="012df-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="012df-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="012df-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="012df-106">Parameters</span></span>  

 `tkParent`  
 <span data-ttu-id="012df-107">de Token para el método del que se va a crear la instancia genérica.</span><span class="sxs-lookup"><span data-stu-id="012df-107">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="012df-108">El token debe ser de tipo `mdMethodDef` o `mdMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="012df-108">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="012df-109">de Puntero a la firma COM+ binaria del método.</span><span class="sxs-lookup"><span data-stu-id="012df-109">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="012df-110">de Tamaño, en bytes, de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="012df-110">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="012df-111">enuncia Token para la definición de la firma de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="012df-111">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="012df-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="012df-112">Requirements</span></span>  

 <span data-ttu-id="012df-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="012df-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="012df-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="012df-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="012df-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="012df-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="012df-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="012df-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012df-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="012df-117">See also</span></span>

- [<span data-ttu-id="012df-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="012df-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="012df-119">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="012df-119">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
