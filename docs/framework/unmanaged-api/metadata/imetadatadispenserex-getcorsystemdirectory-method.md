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
ms.openlocfilehash: a76c17e663fdf6555ed878cca1b86b6a9395730e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008800"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="ee36b-102">IMetaDataDispenserEx::GetCORSystemDirectory (Método)</span><span class="sxs-lookup"><span data-stu-id="ee36b-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="ee36b-103">Obtiene el directorio que contiene el Common Language Runtime actual (CLR).</span><span class="sxs-lookup"><span data-stu-id="ee36b-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="ee36b-104">Este método solo se admite para su uso en depuradores fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="ee36b-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="ee36b-105">Si se llama desde otro componente, devolverá E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ee36b-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee36b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee36b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee36b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee36b-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="ee36b-108">enuncia Búfer en el que se va a recibir el nombre del directorio.</span><span class="sxs-lookup"><span data-stu-id="ee36b-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ee36b-109">de Tamaño, en bytes, de `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="ee36b-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="ee36b-110">enuncia Número de bytes devueltos realmente en `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="ee36b-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee36b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee36b-111">Requirements</span></span>  
 <span data-ttu-id="ee36b-112">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee36b-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee36b-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ee36b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee36b-114">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee36b-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee36b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee36b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee36b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee36b-116">See also</span></span>

- [<span data-ttu-id="ee36b-117">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee36b-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="ee36b-118">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee36b-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
