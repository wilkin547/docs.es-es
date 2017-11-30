---
title: "IAssemblyCacheItem::CreateStream (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem.CreateStream
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8dfdb34e10c6bc47ce13230ee03ef024cb15b07b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="c36a1-102">IAssemblyCacheItem::CreateStream (Método)</span><span class="sxs-lookup"><span data-stu-id="c36a1-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="c36a1-103">Crea una secuencia con el nombre especificado y el formato.</span><span class="sxs-lookup"><span data-stu-id="c36a1-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c36a1-104">Syntax</span></span>  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c36a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c36a1-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="c36a1-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="c36a1-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="c36a1-107">[in] El nombre de la secuencia que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c36a1-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="c36a1-108">[in] El formato del archivo que se transmite por secuencias.</span><span class="sxs-lookup"><span data-stu-id="c36a1-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="c36a1-109">[in] Indicadores específicos del formato definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="c36a1-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="c36a1-110">[out] Un puntero a la dirección de devuelto <xref:IStream> instancia.</span><span class="sxs-lookup"><span data-stu-id="c36a1-110">[out] A pointer to the address of the returned <xref:IStream> instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="c36a1-111">[in, opcional] El tamaño máximo de la secuencia al que hace referencia `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="c36a1-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c36a1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c36a1-112">Requirements</span></span>  
 <span data-ttu-id="c36a1-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c36a1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c36a1-114">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c36a1-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c36a1-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c36a1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36a1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c36a1-116">See Also</span></span>  
 [<span data-ttu-id="c36a1-117">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c36a1-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
