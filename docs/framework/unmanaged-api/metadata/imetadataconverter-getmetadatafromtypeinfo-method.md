---
title: IMetaDataConverter::GetMetaDataFromTypeInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
ms.openlocfilehash: 1f45310bc65bc8614033182a81db451b79bcf97f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714723"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="fc083-102">IMetaDataConverter::GetMetaDataFromTypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="fc083-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>

<span data-ttu-id="fc083-103">Obtiene un puntero a una instancia de [IMetaDataImport](imetadataimport-interface.md) que representa la firma de metadatos de la biblioteca de tipos a la que hace referencia la instancia de especificada `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="fc083-103">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc083-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc083-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc083-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc083-105">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="fc083-106">de Un puntero a un `ITypeInfo` objeto que hace referencia a la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="fc083-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="fc083-107">enuncia Puntero a una ubicación que recibe la dirección de la `IMetaDataImport` instancia de que representa la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="fc083-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc083-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc083-108">Requirements</span></span>  

 <span data-ttu-id="fc083-109">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc083-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc083-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fc083-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc083-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc083-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fc083-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc083-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc083-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc083-113">See also</span></span>

- [<span data-ttu-id="fc083-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc083-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fc083-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc083-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
