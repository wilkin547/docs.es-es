---
description: 'Más información sobre: IMetaDataImport:: GetMethodProps ((método)'
title: IMetaDataImport::GetMethodProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 5fb344d72378a806e0e71820b55a90998e497916
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783889"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="3fe5c-103">IMetaDataImport::GetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="3fe5c-103">IMetaDataImport::GetMethodProps Method</span></span>

<span data-ttu-id="3fe5c-104">Obtiene los metadatos asociados al método al que hace referencia el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="3fe5c-104">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe5c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fe5c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fe5c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3fe5c-106">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="3fe5c-107">de Token de MethodDef que representa el método para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="3fe5c-107">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="3fe5c-108">enuncia Un puntero a un token de TypeDef que representa el tipo que implementa el método.</span><span class="sxs-lookup"><span data-stu-id="3fe5c-108">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="3fe5c-109">enuncia Puntero a un búfer que tiene el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="3fe5c-109">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="3fe5c-110">de Tamaño solicitado de `szMethod` .</span><span class="sxs-lookup"><span data-stu-id="3fe5c-110">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="3fe5c-111">enuncia Puntero al tamaño en caracteres anchos de `szMethod` , o en el caso del truncamiento, el número real de caracteres anchos en el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="3fe5c-111">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="3fe5c-112">enuncia Puntero a cualquier marca asociada al método.</span><span class="sxs-lookup"><span data-stu-id="3fe5c-112">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="3fe5c-113">enuncia Puntero a la firma de metadatos binarios del método.</span><span class="sxs-lookup"><span data-stu-id="3fe5c-113">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="3fe5c-114">enuncia Puntero al tamaño en bytes de `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="3fe5c-114">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="3fe5c-115">enuncia Puntero a la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="3fe5c-115">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="3fe5c-116">enuncia Un puntero a cualquier marcador de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="3fe5c-116">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fe5c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3fe5c-117">Requirements</span></span>  

 <span data-ttu-id="3fe5c-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fe5c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fe5c-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3fe5c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3fe5c-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3fe5c-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3fe5c-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fe5c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe5c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fe5c-122">See also</span></span>

- [<span data-ttu-id="3fe5c-123">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fe5c-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3fe5c-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fe5c-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
