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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 362cbe9ff19e74bafc73fde857d231185179efbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777506"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="042aa-102">IMetaDataImport::GetTypeSpecFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="042aa-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="042aa-103">Obtiene la firma de metadatos binaria de la especificación de tipo representada por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="042aa-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="042aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="042aa-104">Syntax</span></span>  
  
```  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="042aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="042aa-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="042aa-106">[in] El token de TypeSpec asociado con la firma de metadatos solicitada.</span><span class="sxs-lookup"><span data-stu-id="042aa-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="042aa-107">[out] Un puntero a la firma de metadatos binaria.</span><span class="sxs-lookup"><span data-stu-id="042aa-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="042aa-108">[out] El tamaño, en bytes, de la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="042aa-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="042aa-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="042aa-109">Return Value</span></span>  
 <span data-ttu-id="042aa-110">Un HRESULT que indica éxito o error.</span><span class="sxs-lookup"><span data-stu-id="042aa-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="042aa-111">Errores se pueden probar con la macro FAILED.</span><span class="sxs-lookup"><span data-stu-id="042aa-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="042aa-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="042aa-112">Requirements</span></span>  
 <span data-ttu-id="042aa-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="042aa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="042aa-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="042aa-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="042aa-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="042aa-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="042aa-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="042aa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="042aa-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="042aa-117">See also</span></span>

- [<span data-ttu-id="042aa-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="042aa-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="042aa-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="042aa-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
