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
ms.openlocfilehash: 8057406552525be19f8e6457de9faf841edc6e68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429506"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="ee2fd-102">IAssemblyCacheItem::CreateStream (Método)</span><span class="sxs-lookup"><span data-stu-id="ee2fd-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="ee2fd-103">Crea una secuencia con el nombre especificado y el formato.</span><span class="sxs-lookup"><span data-stu-id="ee2fd-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee2fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee2fd-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ee2fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee2fd-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="ee2fd-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="ee2fd-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="ee2fd-107">[in] El nombre de la secuencia que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ee2fd-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="ee2fd-108">[in] El formato del archivo que se transmite por secuencias.</span><span class="sxs-lookup"><span data-stu-id="ee2fd-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="ee2fd-109">[in] Indicadores específicos del formato definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="ee2fd-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="ee2fd-110">[out] Un puntero a la dirección de devuelto [IStream](https://msdn.microsoft.com/library/aa380034.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="ee2fd-110">[out] A pointer to the address of the returned [IStream](https://msdn.microsoft.com/library/aa380034.aspx) instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="ee2fd-111">[in, opcional] El tamaño máximo de la secuencia al que hace referencia `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="ee2fd-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee2fd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee2fd-112">Requirements</span></span>  
 <span data-ttu-id="ee2fd-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee2fd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee2fd-114">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ee2fd-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ee2fd-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee2fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee2fd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee2fd-116">See Also</span></span>  
 [<span data-ttu-id="ee2fd-117">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee2fd-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
