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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050186"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="33d51-102">IMetaDataDispenserEx::GetCORSystemDirectory (Método)</span><span class="sxs-lookup"><span data-stu-id="33d51-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="33d51-103">Obtiene el directorio que contiene el actual common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="33d51-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="33d51-104">Este método es compatible solo para su uso con los depuradores fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="33d51-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="33d51-105">Si se llama desde otro componente, devolverá E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="33d51-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33d51-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33d51-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33d51-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33d51-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="33d51-108">[out] El búfer para recibir el nombre del directorio.</span><span class="sxs-lookup"><span data-stu-id="33d51-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="33d51-109">[in] El tamaño, en bytes, de `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="33d51-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="33d51-110">[out] El número de bytes devueltos realmente en `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="33d51-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33d51-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33d51-111">Requirements</span></span>  
 <span data-ttu-id="33d51-112">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33d51-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33d51-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="33d51-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33d51-114">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33d51-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33d51-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33d51-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d51-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="33d51-116">See also</span></span>

- [<span data-ttu-id="33d51-117">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33d51-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="33d51-118">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33d51-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
