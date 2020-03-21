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
ms.openlocfilehash: ef573eb9a572c27e685289b2740a55e898be2093
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177633"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="0a8b5-102">IMetaDataConverter::GetTypeLibFromMetaData (Método)</span><span class="sxs-lookup"><span data-stu-id="0a8b5-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="0a8b5-103">Obtiene un puntero `ITypeLib` a una instancia que representa la biblioteca de tipos que tiene los nombres de biblioteca y módulo especificados.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a8b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a8b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a8b5-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="0a8b5-106">[en] El nombre del módulo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="0a8b5-107">[en] El nombre de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="0a8b5-108">[fuera] Puntero a una ubicación que recibe `ITypeLib` la dirección de la instancia que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a8b5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a8b5-109">Requirements</span></span>  
 <span data-ttu-id="0a8b5-110">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a8b5-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a8b5-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a8b5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a8b5-112">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a8b5-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a8b5-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a8b5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8b5-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a8b5-114">See also</span></span>

- [<span data-ttu-id="0a8b5-115">IMetaDataConverter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a8b5-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
