---
title: "IMetaDataImport::GetNativeCallConvFromSig (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNativeCallConvFromSig
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5bcd54d4c0a0a1ac4dcb98e51fc25e5f3a7c7288
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="3337a-102">IMetaDataImport::GetNativeCallConvFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="3337a-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="3337a-103">Obtiene la convención de llamada nativa del método representado por el puntero de firma especificado.</span><span class="sxs-lookup"><span data-stu-id="3337a-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3337a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3337a-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3337a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3337a-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="3337a-106">[in] Un puntero a la firma de metadatos del método para devolver la convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="3337a-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="3337a-107">[in] El tamaño en bytes de `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="3337a-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="3337a-108">[out] Un puntero a la convención de llamada nativa.</span><span class="sxs-lookup"><span data-stu-id="3337a-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3337a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3337a-109">Requirements</span></span>  
 <span data-ttu-id="3337a-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3337a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3337a-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3337a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3337a-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3337a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3337a-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3337a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3337a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3337a-114">See Also</span></span>  
 <xref:System.Runtime.InteropServices.CallingConvention>  
 [<span data-ttu-id="3337a-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3337a-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3337a-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3337a-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
