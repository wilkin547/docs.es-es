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
ms.openlocfilehash: deecd9ed4161bbd72e97a6320188961ae76d1e7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218789"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="bbdb2-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="bbdb2-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="bbdb2-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="bbdb2-103">This method is not implemented.</span></span> <span data-ttu-id="bbdb2-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="bbdb2-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbdb2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbdb2-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbdb2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bbdb2-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="bbdb2-107">[in] Puntero a un [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interfaz que proporciona la información de tipo en el que se va a abrir el ámbito.</span><span class="sxs-lookup"><span data-stu-id="bbdb2-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="bbdb2-108">[in] Las marcas de modo de apertura.</span><span class="sxs-lookup"><span data-stu-id="bbdb2-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="bbdb2-109">[in] La interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="bbdb2-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="bbdb2-110">[out] Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="bbdb2-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbdb2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbdb2-111">Requirements</span></span>  
 <span data-ttu-id="bbdb2-112">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbdb2-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbdb2-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="bbdb2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bbdb2-114">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bbdb2-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bbdb2-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbdb2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbdb2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbdb2-116">See also</span></span>

- [<span data-ttu-id="bbdb2-117">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bbdb2-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="bbdb2-118">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bbdb2-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
