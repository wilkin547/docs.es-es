---
title: IAssemblyCacheItem::CreateStream (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a0b3242e8ae29b9d21dc50d3ea0476967e9746f
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171977"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="415e7-102">IAssemblyCacheItem::CreateStream (Método)</span><span class="sxs-lookup"><span data-stu-id="415e7-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="415e7-103">Crea una secuencia con el nombre especificado y el formato.</span><span class="sxs-lookup"><span data-stu-id="415e7-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="415e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="415e7-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="415e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="415e7-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="415e7-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="415e7-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="415e7-107">[in] El nombre de la secuencia que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="415e7-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="415e7-108">[in] El formato del archivo que se transmite por secuencias.</span><span class="sxs-lookup"><span data-stu-id="415e7-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="415e7-109">[in] Marcas de formato específicos definidas en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="415e7-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="415e7-110">[out] Un puntero a la dirección de devuelto [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instancia.</span><span class="sxs-lookup"><span data-stu-id="415e7-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="415e7-111">[in, optional] El tamaño máximo de la secuencia al que hace referencia `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="415e7-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="415e7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="415e7-112">Requirements</span></span>  
 <span data-ttu-id="415e7-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="415e7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="415e7-114">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="415e7-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="415e7-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="415e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415e7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="415e7-116">See Also</span></span>  
 [<span data-ttu-id="415e7-117">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="415e7-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
