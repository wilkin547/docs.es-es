---
title: "IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45c65d0194ed44122a87dcd000359187fc020d0e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="a0249-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="a0249-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="a0249-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="a0249-103">This method is not implemented.</span></span> <span data-ttu-id="a0249-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a0249-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0249-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0249-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0249-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0249-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="a0249-107">[in] Puntero a un [ITypeInfo](http://msdn.microsoft.com/library/f3356463-3373-4279-bae1-953378aa2680) interfaz que proporciona la información de tipo en el que se va a abrir el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a0249-107">[in] Pointer to an [ITypeInfo](http://msdn.microsoft.com/library/f3356463-3373-4279-bae1-953378aa2680) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a0249-108">[in] Las marcas de modo de apertura.</span><span class="sxs-lookup"><span data-stu-id="a0249-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="a0249-109">[in] La interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="a0249-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="a0249-110">[out] Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="a0249-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0249-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0249-111">Requirements</span></span>  
 <span data-ttu-id="a0249-112">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0249-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0249-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a0249-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0249-114">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0249-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0249-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0249-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0249-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0249-116">See Also</span></span>  
 [<span data-ttu-id="a0249-117">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0249-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="a0249-118">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0249-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
