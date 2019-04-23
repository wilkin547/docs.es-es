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
ms.openlocfilehash: 35e780c330d0184d40bd99f34c3454f83075c1e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139287"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="c0821-102">IMetaDataImport::GetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="c0821-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="c0821-103">Obtiene un puntero al tipo nativo y no administrado del campo representado por el token de metadatos del campo especificado.</span><span class="sxs-lookup"><span data-stu-id="c0821-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0821-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0821-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0821-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0821-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c0821-106">[in] El token de metadatos que representa el campo para obtener información de serialización de interoperabilidad para.</span><span class="sxs-lookup"><span data-stu-id="c0821-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="c0821-107">[out] Un puntero a la firma de metadatos de tipo nativo del campo.</span><span class="sxs-lookup"><span data-stu-id="c0821-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="c0821-108">[out] El tamaño en bytes de `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="c0821-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0821-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0821-109">Requirements</span></span>  
 <span data-ttu-id="c0821-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0821-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0821-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0821-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0821-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0821-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0821-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0821-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0821-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0821-114">See also</span></span>

- [<span data-ttu-id="c0821-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0821-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c0821-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0821-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
