---
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
ms.openlocfilehash: 4a258ce9121a287929ca5bc39c480f1ca2596e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437463"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="d85b9-102">IMetaDataImport::GetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="d85b9-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="d85b9-103">Obtiene los metadatos asociados al método al que hace referencia el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="d85b9-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d85b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d85b9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d85b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d85b9-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="d85b9-106">de Token de MethodDef que representa el método para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="d85b9-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="d85b9-107">enuncia Un puntero a un token de TypeDef que representa el tipo que implementa el método.</span><span class="sxs-lookup"><span data-stu-id="d85b9-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="d85b9-108">enuncia Puntero a un búfer que tiene el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="d85b9-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="d85b9-109">de Tamaño solicitado de `szMethod`.</span><span class="sxs-lookup"><span data-stu-id="d85b9-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="d85b9-110">enuncia Puntero al tamaño en caracteres anchos de `szMethod`, o en el caso del truncamiento, el número real de caracteres anchos en el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="d85b9-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="d85b9-111">enuncia Puntero a cualquier marca asociada al método.</span><span class="sxs-lookup"><span data-stu-id="d85b9-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="d85b9-112">enuncia Puntero a la firma de metadatos binarios del método.</span><span class="sxs-lookup"><span data-stu-id="d85b9-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="d85b9-113">enuncia Puntero al tamaño en bytes de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="d85b9-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="d85b9-114">enuncia Puntero a la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="d85b9-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="d85b9-115">enuncia Un puntero a cualquier marcador de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="d85b9-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d85b9-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d85b9-116">Requirements</span></span>  
 <span data-ttu-id="d85b9-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d85b9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d85b9-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d85b9-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d85b9-119">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d85b9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d85b9-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d85b9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d85b9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d85b9-121">See also</span></span>

- [<span data-ttu-id="d85b9-122">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d85b9-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d85b9-123">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d85b9-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
