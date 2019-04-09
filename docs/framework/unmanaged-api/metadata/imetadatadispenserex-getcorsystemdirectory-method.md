---
title: IMetaDataDispenserEx::GetCORSystemDirectory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3dbfca942d61cd5667293d11f358f06bd000fa2e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118006"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="10171-102">IMetaDataDispenserEx::GetCORSystemDirectory (Método)</span><span class="sxs-lookup"><span data-stu-id="10171-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="10171-103">Obtiene el directorio que contiene el actual common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="10171-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="10171-104">Este método es compatible solo para su uso con los depuradores fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="10171-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="10171-105">Si se llama desde otro componente, devolverá E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="10171-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10171-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10171-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10171-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10171-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="10171-108">[out] El búfer para recibir el nombre del directorio.</span><span class="sxs-lookup"><span data-stu-id="10171-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="10171-109">[in] El tamaño, en bytes, de `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="10171-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="10171-110">[out] El número de bytes devueltos realmente en `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="10171-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10171-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10171-111">Requirements</span></span>  
 <span data-ttu-id="10171-112">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10171-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10171-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="10171-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10171-114">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10171-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="10171-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="10171-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="10171-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="10171-116">See also</span></span>

- [<span data-ttu-id="10171-117">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10171-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="10171-118">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10171-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
