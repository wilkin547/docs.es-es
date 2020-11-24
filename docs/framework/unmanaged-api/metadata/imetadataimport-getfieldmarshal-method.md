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
ms.openlocfilehash: 35f73135dbeea1c79d15e0a9e9367c5d533487ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676871"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="e6d38-102">IMetaDataImport::GetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="e6d38-102">IMetaDataImport::GetFieldMarshal Method</span></span>

<span data-ttu-id="e6d38-103">Obtiene un puntero al tipo nativo no administrado del campo representado por el token de metadatos de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="e6d38-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6d38-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6d38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6d38-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="e6d38-106">de Token de metadatos que representa el campo para el que se va a obtener información de serialización de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="e6d38-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="e6d38-107">enuncia Puntero a la firma de metadatos del tipo nativo del campo.</span><span class="sxs-lookup"><span data-stu-id="e6d38-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="e6d38-108">enuncia Tamaño en bytes de `ppvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="e6d38-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6d38-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6d38-109">Requirements</span></span>  

 <span data-ttu-id="e6d38-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6d38-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6d38-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e6d38-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6d38-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6d38-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e6d38-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d38-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d38-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6d38-114">See also</span></span>

- [<span data-ttu-id="e6d38-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6d38-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e6d38-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6d38-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
