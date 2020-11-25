---
title: IMetaDataImport::GetSigFromToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
ms.openlocfilehash: 67abdfd8f8c67299eae757533f20df69392f25b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729192"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="fcf09-102">IMetaDataImport::GetSigFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="fcf09-102">IMetaDataImport::GetSigFromToken Method</span></span>

<span data-ttu-id="fcf09-103">Obtiene la firma de metadatos binaria asociada al token especificado.</span><span class="sxs-lookup"><span data-stu-id="fcf09-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcf09-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcf09-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fcf09-105">Parameters</span></span>  

 `mdSig`  
 <span data-ttu-id="fcf09-106">de Token para el que se va a devolver la firma de metadatos binarios.</span><span class="sxs-lookup"><span data-stu-id="fcf09-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="fcf09-107">enuncia Puntero a la firma de metadatos devuelta.</span><span class="sxs-lookup"><span data-stu-id="fcf09-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="fcf09-108">enuncia Tamaño en bytes de la firma de metadatos binarios.</span><span class="sxs-lookup"><span data-stu-id="fcf09-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcf09-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcf09-109">Requirements</span></span>  

 <span data-ttu-id="fcf09-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcf09-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcf09-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fcf09-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fcf09-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fcf09-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fcf09-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf09-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf09-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcf09-114">See also</span></span>

- [<span data-ttu-id="fcf09-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fcf09-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="fcf09-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fcf09-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
