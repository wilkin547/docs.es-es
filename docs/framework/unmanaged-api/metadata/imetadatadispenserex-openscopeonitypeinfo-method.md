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
ms.openlocfilehash: 8e119093800ea0a0119ba25ba38cf2eaf9afe96b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540867"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="a1aeb-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="a1aeb-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="a1aeb-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="a1aeb-103">This method is not implemented.</span></span> <span data-ttu-id="a1aeb-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a1aeb-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1aeb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1aeb-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1aeb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1aeb-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="a1aeb-107">de Puntero a una interfaz [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) que proporciona la información de tipo en la que se va a abrir el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a1aeb-107">[in] Pointer to an [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a1aeb-108">de Marcas de modo de apertura.</span><span class="sxs-lookup"><span data-stu-id="a1aeb-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="a1aeb-109">de La interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="a1aeb-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="a1aeb-110">enuncia Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="a1aeb-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1aeb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1aeb-111">Requirements</span></span>  
 <span data-ttu-id="a1aeb-112">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1aeb-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1aeb-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a1aeb-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1aeb-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1aeb-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1aeb-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1aeb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1aeb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1aeb-116">See also</span></span>

- [<span data-ttu-id="a1aeb-117">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1aeb-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="a1aeb-118">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1aeb-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
