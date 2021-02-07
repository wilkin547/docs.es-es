---
description: 'Más información sobre: IMetaDataDispenserEx:: Openscopeonitypeinfo ((método)'
title: IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
ms.openlocfilehash: bc36bac9e7c63f56f442f1e25fd7a6a93f75924b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753528"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="f377a-103">IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="f377a-103">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>

<span data-ttu-id="f377a-104">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="f377a-104">This method is not implemented.</span></span> <span data-ttu-id="f377a-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f377a-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f377a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f377a-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f377a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f377a-107">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="f377a-108">de Puntero a una interfaz [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) que proporciona la información de tipo en la que se va a abrir el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f377a-108">[in] Pointer to an [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="f377a-109">de Marcas de modo de apertura.</span><span class="sxs-lookup"><span data-stu-id="f377a-109">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="f377a-110">de La interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="f377a-110">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="f377a-111">enuncia Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="f377a-111">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f377a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f377a-112">Requirements</span></span>  

 <span data-ttu-id="f377a-113">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f377a-113">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f377a-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f377a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f377a-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f377a-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f377a-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f377a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f377a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f377a-117">See also</span></span>

- [<span data-ttu-id="f377a-118">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f377a-118">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="f377a-119">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f377a-119">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
