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
ms.openlocfilehash: da9a13a3dea34f6681f47e95c5b352a710d7458b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431212"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="82c8c-102">IMetaDataDispenserEx::GetCORSystemDirectory (Método)</span><span class="sxs-lookup"><span data-stu-id="82c8c-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="82c8c-103">Obtiene el directorio que contiene el Common Language Runtime actual (CLR).</span><span class="sxs-lookup"><span data-stu-id="82c8c-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="82c8c-104">Este método solo se admite para su uso en depuradores fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="82c8c-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="82c8c-105">Si se llama desde otro componente, devolverá E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="82c8c-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82c8c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82c8c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82c8c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82c8c-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="82c8c-108">enuncia Búfer en el que se va a recibir el nombre del directorio.</span><span class="sxs-lookup"><span data-stu-id="82c8c-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="82c8c-109">de Tamaño, en bytes, de `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82c8c-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="82c8c-110">enuncia Número de bytes realmente devueltos en `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82c8c-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82c8c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82c8c-111">Requirements</span></span>  
 <span data-ttu-id="82c8c-112">**Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82c8c-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82c8c-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="82c8c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82c8c-114">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="82c8c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82c8c-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82c8c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c8c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="82c8c-116">See also</span></span>

- [<span data-ttu-id="82c8c-117">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82c8c-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="82c8c-118">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82c8c-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
