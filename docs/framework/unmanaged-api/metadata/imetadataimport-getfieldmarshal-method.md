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
ms.openlocfilehash: 91a19e5e15dddd446208dfa3b2c32826282067eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175400"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="44a23-102">IMetaDataImport::GetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="44a23-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="44a23-103">Obtiene un puntero al tipo nativo no administrado del campo representado por el token de metadatos de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="44a23-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44a23-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44a23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44a23-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44a23-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="44a23-106">[en] El token de metadatos que representa el campo para el que obtener información de cálculo de referencias de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="44a23-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="44a23-107">[fuera] Puntero a la firma de metadatos del tipo nativo del campo.</span><span class="sxs-lookup"><span data-stu-id="44a23-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="44a23-108">[fuera] El tamaño en `ppvNativeType`bytes de .</span><span class="sxs-lookup"><span data-stu-id="44a23-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44a23-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44a23-109">Requirements</span></span>  
 <span data-ttu-id="44a23-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44a23-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44a23-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="44a23-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44a23-112">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44a23-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44a23-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44a23-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44a23-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44a23-114">See also</span></span>

- [<span data-ttu-id="44a23-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="44a23-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="44a23-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="44a23-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
