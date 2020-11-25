---
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
ms.openlocfilehash: 62495aa4280bb1799af09fea2e550ae6107e09e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729153"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="33028-102">IMetaDataImport::GetTypeSpecFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="33028-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>

<span data-ttu-id="33028-103">Obtiene la firma de metadatos binaria de la especificación de tipo representada por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="33028-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33028-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33028-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33028-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33028-105">Parameters</span></span>  

 `typespec`  
 <span data-ttu-id="33028-106">de El token TypeSpec asociado a la firma de metadatos solicitada.</span><span class="sxs-lookup"><span data-stu-id="33028-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="33028-107">enuncia Puntero a la firma de metadatos binarios.</span><span class="sxs-lookup"><span data-stu-id="33028-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="33028-108">enuncia Tamaño, en bytes, de la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="33028-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33028-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33028-109">Return Value</span></span>  

 <span data-ttu-id="33028-110">HRESULT que indica si se ha realizado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="33028-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="33028-111">Los errores se pueden probar con la macro FAILed.</span><span class="sxs-lookup"><span data-stu-id="33028-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33028-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33028-112">Requirements</span></span>  

 <span data-ttu-id="33028-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33028-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33028-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="33028-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33028-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33028-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33028-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33028-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33028-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33028-117">See also</span></span>

- [<span data-ttu-id="33028-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33028-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="33028-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33028-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
