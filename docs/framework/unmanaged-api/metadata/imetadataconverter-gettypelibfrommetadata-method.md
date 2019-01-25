---
title: IMetaDataConverter::GetTypeLibFromMetaData (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a6c39989a37f46d684c3a467d5e099ea7167185
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624137"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="ad3c1-102">IMetaDataConverter::GetTypeLibFromMetaData (Método)</span><span class="sxs-lookup"><span data-stu-id="ad3c1-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="ad3c1-103">Obtiene un puntero a un `ITypeLib` instancia que representa la biblioteca de tipos con los nombres de biblioteca y el módulo especificados.</span><span class="sxs-lookup"><span data-stu-id="ad3c1-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad3c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad3c1-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad3c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad3c1-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="ad3c1-106">[in] El nombre del módulo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="ad3c1-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="ad3c1-107">[in] El nombre de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="ad3c1-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="ad3c1-108">[out] Un puntero a una ubicación que recibe la dirección de la `ITypeLib` instancia que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="ad3c1-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad3c1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad3c1-109">Requirements</span></span>  
 <span data-ttu-id="ad3c1-110">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad3c1-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad3c1-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ad3c1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad3c1-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad3c1-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad3c1-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad3c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3c1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad3c1-114">See also</span></span>
- [<span data-ttu-id="ad3c1-115">IMetaDataConverter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad3c1-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
