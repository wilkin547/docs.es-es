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
ms.openlocfilehash: 73866ef2dc7069708887c128f977f730519603bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446028"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="5ba1b-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="5ba1b-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="5ba1b-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="5ba1b-103">This method is not implemented.</span></span> <span data-ttu-id="5ba1b-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="5ba1b-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ba1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ba1b-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ba1b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ba1b-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="5ba1b-107">[in] Puntero a un [ITypeInfo](http://msdn.microsoft.com/library/f3356463-3373-4279-bae1-953378aa2680) interfaz que proporciona la información de tipo en el que se va a abrir el ámbito.</span><span class="sxs-lookup"><span data-stu-id="5ba1b-107">[in] Pointer to an [ITypeInfo](http://msdn.microsoft.com/library/f3356463-3373-4279-bae1-953378aa2680) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="5ba1b-108">[in] Las marcas de modo de apertura.</span><span class="sxs-lookup"><span data-stu-id="5ba1b-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="5ba1b-109">[in] La interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="5ba1b-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="5ba1b-110">[out] Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="5ba1b-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ba1b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ba1b-111">Requirements</span></span>  
 <span data-ttu-id="5ba1b-112">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ba1b-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ba1b-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ba1b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ba1b-114">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ba1b-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ba1b-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ba1b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba1b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ba1b-116">See Also</span></span>  
 [<span data-ttu-id="5ba1b-117">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ba1b-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="5ba1b-118">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ba1b-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
