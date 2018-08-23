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
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754565"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="9a048-102">IAssemblyCacheItem::CreateStream (Método)</span><span class="sxs-lookup"><span data-stu-id="9a048-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="9a048-103">Crea una secuencia con el nombre especificado y el formato.</span><span class="sxs-lookup"><span data-stu-id="9a048-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a048-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a048-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="9a048-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a048-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="9a048-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="9a048-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="9a048-107">[in] El nombre de la secuencia que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="9a048-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="9a048-108">[in] El formato del archivo que se transmite por secuencias.</span><span class="sxs-lookup"><span data-stu-id="9a048-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="9a048-109">[in] Marcas de formato específicos definidas en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="9a048-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="9a048-110">[out] Un puntero a la dirección de devuelto [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instancia.</span><span class="sxs-lookup"><span data-stu-id="9a048-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="9a048-111">[in, optional] El tamaño máximo de la secuencia al que hace referencia `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="9a048-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a048-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a048-112">Requirements</span></span>  
 <span data-ttu-id="9a048-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a048-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a048-114">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="9a048-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9a048-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a048-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a048-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a048-116">See Also</span></span>  
 [<span data-ttu-id="9a048-117">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a048-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
