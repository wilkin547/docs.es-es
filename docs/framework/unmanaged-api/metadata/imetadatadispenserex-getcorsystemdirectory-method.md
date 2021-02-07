---
description: 'Más información sobre: IMetaDataDispenserEx:: GetCORSystemDirectory ((método)'
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
ms.openlocfilehash: 3ceda653e50ba5ad7de5548b78781f48cda41624
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753567"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="3e76e-103">IMetaDataDispenserEx::GetCORSystemDirectory (Método)</span><span class="sxs-lookup"><span data-stu-id="3e76e-103">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>

<span data-ttu-id="3e76e-104">Obtiene el directorio que contiene el Common Language Runtime actual (CLR).</span><span class="sxs-lookup"><span data-stu-id="3e76e-104">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="3e76e-105">Este método solo se admite para su uso en depuradores fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="3e76e-105">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="3e76e-106">Si se llama desde otro componente, devolverá E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="3e76e-106">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e76e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e76e-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e76e-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e76e-108">Parameters</span></span>  

 `szBuffer`  
 <span data-ttu-id="3e76e-109">enuncia Búfer en el que se va a recibir el nombre del directorio.</span><span class="sxs-lookup"><span data-stu-id="3e76e-109">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="3e76e-110">de Tamaño, en bytes, de `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="3e76e-110">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="3e76e-111">enuncia Número de bytes devueltos realmente en `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="3e76e-111">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e76e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e76e-112">Requirements</span></span>  

 <span data-ttu-id="3e76e-113">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e76e-113">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e76e-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3e76e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e76e-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e76e-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e76e-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e76e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e76e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e76e-117">See also</span></span>

- [<span data-ttu-id="3e76e-118">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e76e-118">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="3e76e-119">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e76e-119">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
