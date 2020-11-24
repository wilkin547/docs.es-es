---
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
ms.openlocfilehash: 6056a64b354f69ce39692173da01892870fba9e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682853"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="8dd6c-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="8dd6c-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>

<span data-ttu-id="8dd6c-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-103">This method is not implemented.</span></span> <span data-ttu-id="8dd6c-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dd6c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8dd6c-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dd6c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8dd6c-106">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="8dd6c-107">de Puntero a una interfaz [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) que proporciona la información de tipo en la que se va a abrir el ámbito.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-107">[in] Pointer to an [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="8dd6c-108">de Marcas de modo de apertura.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="8dd6c-109">de La interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="8dd6c-110">enuncia Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="8dd6c-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dd6c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8dd6c-111">Requirements</span></span>  

 <span data-ttu-id="8dd6c-112">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dd6c-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dd6c-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8dd6c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8dd6c-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8dd6c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8dd6c-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dd6c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd6c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8dd6c-116">See also</span></span>

- [<span data-ttu-id="8dd6c-117">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8dd6c-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="8dd6c-118">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8dd6c-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
