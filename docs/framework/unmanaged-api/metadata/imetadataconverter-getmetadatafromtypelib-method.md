---
title: IMetaDataConverter::GetMetaDataFromTypeLib (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cdc1b0de9795a000ee680df880c73acc4f711db2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145332"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="9db87-102">IMetaDataConverter::GetMetaDataFromTypeLib (Método)</span><span class="sxs-lookup"><span data-stu-id="9db87-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="9db87-103">Obtiene un puntero de interfaz a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instancia que representa la firma de metadatos de la biblioteca de tipos representada por el `ITypeLib` instancia.</span><span class="sxs-lookup"><span data-stu-id="9db87-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9db87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9db87-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9db87-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9db87-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="9db87-106">[in] Puntero a un `ITypeLib` objeto que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="9db87-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="9db87-107">[out] Puntero a una ubicación que recibe la dirección de la `IMetaDataImport` instancia que representa la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9db87-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9db87-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9db87-108">Requirements</span></span>  
 <span data-ttu-id="9db87-109">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9db87-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9db87-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="9db87-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9db87-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9db87-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="9db87-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9db87-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9db87-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9db87-113">See also</span></span>

- [<span data-ttu-id="9db87-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9db87-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9db87-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9db87-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
