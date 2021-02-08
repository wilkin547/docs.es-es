---
description: 'Más información sobre: IMetaDataImport:: Getfieldmarshal ((método)'
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
ms.openlocfilehash: d6ca1f80a8b9bae4d9c02466042300bc3662f7c3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803534"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="22a98-103">IMetaDataImport::GetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="22a98-103">IMetaDataImport::GetFieldMarshal Method</span></span>

<span data-ttu-id="22a98-104">Obtiene un puntero al tipo nativo no administrado del campo representado por el token de metadatos de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="22a98-104">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a98-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22a98-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22a98-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22a98-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="22a98-107">de Token de metadatos que representa el campo para el que se va a obtener información de serialización de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="22a98-107">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="22a98-108">enuncia Puntero a la firma de metadatos del tipo nativo del campo.</span><span class="sxs-lookup"><span data-stu-id="22a98-108">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="22a98-109">enuncia Tamaño en bytes de `ppvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="22a98-109">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22a98-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22a98-110">Requirements</span></span>  

 <span data-ttu-id="22a98-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22a98-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22a98-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="22a98-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22a98-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22a98-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22a98-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22a98-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a98-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="22a98-115">See also</span></span>

- [<span data-ttu-id="22a98-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22a98-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="22a98-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22a98-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
