---
description: 'Más información sobre: IMetaDataImport:: GetSigFromToken ((método)'
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
ms.openlocfilehash: 16b77fe5866319e24b33ec4ce9d2d56797f04514
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789143"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="11960-103">IMetaDataImport::GetSigFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="11960-103">IMetaDataImport::GetSigFromToken Method</span></span>

<span data-ttu-id="11960-104">Obtiene la firma de metadatos binaria asociada al token especificado.</span><span class="sxs-lookup"><span data-stu-id="11960-104">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11960-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11960-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11960-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11960-106">Parameters</span></span>  

 `mdSig`  
 <span data-ttu-id="11960-107">de Token para el que se va a devolver la firma de metadatos binarios.</span><span class="sxs-lookup"><span data-stu-id="11960-107">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="11960-108">enuncia Puntero a la firma de metadatos devuelta.</span><span class="sxs-lookup"><span data-stu-id="11960-108">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="11960-109">enuncia Tamaño en bytes de la firma de metadatos binarios.</span><span class="sxs-lookup"><span data-stu-id="11960-109">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11960-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11960-110">Requirements</span></span>  

 <span data-ttu-id="11960-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11960-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11960-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="11960-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11960-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11960-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11960-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11960-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11960-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="11960-115">See also</span></span>

- [<span data-ttu-id="11960-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11960-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="11960-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11960-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
