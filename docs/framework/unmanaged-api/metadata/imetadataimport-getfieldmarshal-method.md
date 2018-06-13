---
title: IMetaDataImport::GetFieldMarshal (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 837b2142e200e224fe32c2c673be0f317633452a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445363"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="4bfbf-102">IMetaDataImport::GetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="4bfbf-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="4bfbf-103">Obtiene un puntero al tipo nativo y no administrado del campo representado por el token de metadatos de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="4bfbf-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bfbf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bfbf-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bfbf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4bfbf-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="4bfbf-106">[in] El token de metadatos que representa el campo para obtener información de cálculo de referencias de interoperabilidad de.</span><span class="sxs-lookup"><span data-stu-id="4bfbf-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="4bfbf-107">[out] Un puntero a la firma de metadatos de tipo nativo del campo.</span><span class="sxs-lookup"><span data-stu-id="4bfbf-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="4bfbf-108">[out] El tamaño en bytes de `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="4bfbf-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bfbf-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4bfbf-109">Requirements</span></span>  
 <span data-ttu-id="4bfbf-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bfbf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bfbf-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4bfbf-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4bfbf-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4bfbf-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4bfbf-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bfbf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfbf-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bfbf-114">See Also</span></span>  
 [<span data-ttu-id="4bfbf-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4bfbf-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="4bfbf-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4bfbf-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
