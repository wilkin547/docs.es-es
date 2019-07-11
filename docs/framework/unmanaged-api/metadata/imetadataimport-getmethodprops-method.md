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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 27b2867019085bf5b44f2ee364c07af66144d4b5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782337"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="b4e2f-102">IMetaDataImport::GetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="b4e2f-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="b4e2f-103">Obtiene los metadatos asociados al método al que hace referencia el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4e2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4e2f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b4e2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4e2f-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="b4e2f-106">[in] El token de MethodDef que representa el método para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="b4e2f-107">[out] Un puntero a un token de TypeDef que representa el tipo que implementa el método.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="b4e2f-108">[out] Un puntero a un búfer que contiene el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="b4e2f-109">[in] El tamaño solicitado del `szMethod`.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="b4e2f-110">[out] Un puntero al tamaño en caracteres anchos de `szMethod`, o en el caso de truncamiento, el número real de caracteres anchos en el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="b4e2f-111">[out] Un puntero a cualquier indicador asociado al método.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="b4e2f-112">[out] Un puntero a la firma de metadatos binaria del método.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="b4e2f-113">[out] Un puntero al tamaño en bytes de `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="b4e2f-114">[out] Un puntero a la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="b4e2f-115">[out] Un puntero a los marcadores de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="b4e2f-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4e2f-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4e2f-116">Requirements</span></span>  
 <span data-ttu-id="b4e2f-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4e2f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4e2f-118">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b4e2f-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4e2f-119">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4e2f-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4e2f-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4e2f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4e2f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4e2f-121">See also</span></span>

- [<span data-ttu-id="b4e2f-122">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4e2f-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b4e2f-123">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4e2f-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
