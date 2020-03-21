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
ms.openlocfilehash: fb673666543bea3df44005ee3b20d311524f51d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175920"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="c6c21-102">IMetaDataDispenserEx::GetCORSystemDirectory (Método)</span><span class="sxs-lookup"><span data-stu-id="c6c21-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="c6c21-103">Obtiene el directorio que contiene Common Language Runtime (CLR) actual.</span><span class="sxs-lookup"><span data-stu-id="c6c21-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="c6c21-104">Este método solo se admite para su uso por depuradores fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="c6c21-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="c6c21-105">Si se llama desde otro componente, se devolverá E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c6c21-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c21-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6c21-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6c21-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6c21-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="c6c21-108">[fuera] El búfer para recibir el nombre del directorio.</span><span class="sxs-lookup"><span data-stu-id="c6c21-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="c6c21-109">[en] El tamaño, en `szBuffer`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="c6c21-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="c6c21-110">[fuera] El número de bytes `szBuffer`realmente devueltos en .</span><span class="sxs-lookup"><span data-stu-id="c6c21-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c21-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6c21-111">Requirements</span></span>  
 <span data-ttu-id="c6c21-112">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6c21-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6c21-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6c21-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6c21-114">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6c21-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6c21-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6c21-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c21-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6c21-116">See also</span></span>

- [<span data-ttu-id="c6c21-117">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6c21-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="c6c21-118">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6c21-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
