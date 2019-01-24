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
ms.openlocfilehash: 7ba8cb8cdf89fc07238a9d5f788c76b0cb7f7153
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681344"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="a9a9b-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="a9a9b-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="a9a9b-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="a9a9b-103">This method is not implemented.</span></span> <span data-ttu-id="a9a9b-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a9a9b-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9a9b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9a9b-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9a9b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9a9b-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="a9a9b-107">[in] Puntero a un [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interfaz que proporciona la información de tipo en el que se va a abrir el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a9a9b-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a9a9b-108">[in] Las marcas de modo de apertura.</span><span class="sxs-lookup"><span data-stu-id="a9a9b-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="a9a9b-109">[in] La interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="a9a9b-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="a9a9b-110">[out] Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="a9a9b-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9a9b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9a9b-111">Requirements</span></span>  
 <span data-ttu-id="a9a9b-112">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9a9b-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9a9b-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9a9b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9a9b-114">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9a9b-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9a9b-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9a9b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a9b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9a9b-116">See also</span></span>
- [<span data-ttu-id="a9a9b-117">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9a9b-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="a9a9b-118">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9a9b-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
