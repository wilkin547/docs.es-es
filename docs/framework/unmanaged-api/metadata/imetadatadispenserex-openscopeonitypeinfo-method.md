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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 122a31fab3bf7bf10eb2490a955fb8245ea0408b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471035"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="caf55-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="caf55-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="caf55-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="caf55-103">This method is not implemented.</span></span> <span data-ttu-id="caf55-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="caf55-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caf55-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="caf55-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caf55-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="caf55-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="caf55-107">[in] Puntero a un [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interfaz que proporciona la información de tipo en el que se va a abrir el ámbito.</span><span class="sxs-lookup"><span data-stu-id="caf55-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="caf55-108">[in] Las marcas de modo de apertura.</span><span class="sxs-lookup"><span data-stu-id="caf55-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="caf55-109">[in] La interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="caf55-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="caf55-110">[out] Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="caf55-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caf55-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="caf55-111">Requirements</span></span>  
 <span data-ttu-id="caf55-112">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caf55-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caf55-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="caf55-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="caf55-114">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="caf55-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="caf55-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caf55-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caf55-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="caf55-116">See also</span></span>
- [<span data-ttu-id="caf55-117">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="caf55-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="caf55-118">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="caf55-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
