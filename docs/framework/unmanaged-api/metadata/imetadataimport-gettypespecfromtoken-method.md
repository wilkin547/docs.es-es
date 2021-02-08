---
description: 'Más información sobre: IMetaDataImport:: Gettypespecfromtoken ((método)'
title: IMetaDataImport::GetTypeSpecFromToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
ms.openlocfilehash: b71f8f856da517b3e5046c20d787a555816fb728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789117"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="233a4-103">IMetaDataImport::GetTypeSpecFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="233a4-103">IMetaDataImport::GetTypeSpecFromToken Method</span></span>

<span data-ttu-id="233a4-104">Obtiene la firma de metadatos binaria de la especificación de tipo representada por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="233a4-104">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="233a4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="233a4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="233a4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="233a4-106">Parameters</span></span>  

 `typespec`  
 <span data-ttu-id="233a4-107">de El token TypeSpec asociado a la firma de metadatos solicitada.</span><span class="sxs-lookup"><span data-stu-id="233a4-107">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="233a4-108">enuncia Puntero a la firma de metadatos binarios.</span><span class="sxs-lookup"><span data-stu-id="233a4-108">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="233a4-109">enuncia Tamaño, en bytes, de la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="233a4-109">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="233a4-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="233a4-110">Return Value</span></span>  

 <span data-ttu-id="233a4-111">HRESULT que indica si se ha realizado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="233a4-111">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="233a4-112">Los errores se pueden probar con la macro FAILed.</span><span class="sxs-lookup"><span data-stu-id="233a4-112">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="233a4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="233a4-113">Requirements</span></span>  

 <span data-ttu-id="233a4-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="233a4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="233a4-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="233a4-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="233a4-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="233a4-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="233a4-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="233a4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="233a4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="233a4-118">See also</span></span>

- [<span data-ttu-id="233a4-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="233a4-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="233a4-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="233a4-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
