---
title: IMetaDataImport::GetClassLayout (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 5a442d8d0916b0e86f25c03507de66fc999f2159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711265"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="ef7e3-102">IMetaDataImport::GetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="ef7e3-102">IMetaDataImport::GetClassLayout Method</span></span>

<span data-ttu-id="ef7e3-103">Obtiene la información de diseño de la clase a la que hace referencia el token TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="ef7e3-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef7e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef7e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef7e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef7e3-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="ef7e3-106">de El token de TypeDef para la clase con el diseño que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="ef7e3-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="ef7e3-107">enuncia Uno de los valores 1, 2, 4, 8 o 16 que representa el tamaño de paquete de la clase.</span><span class="sxs-lookup"><span data-stu-id="ef7e3-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="ef7e3-108">enuncia Matriz de valores de [COR_FIELD_OFFSET](cor-field-offset-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="ef7e3-108">[out] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ef7e3-109">[in] Tamaño máximo de la matriz `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="ef7e3-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="ef7e3-110">enuncia Número de elementos devueltos en `rFieldOffset` .</span><span class="sxs-lookup"><span data-stu-id="ef7e3-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="ef7e3-111">enuncia Tamaño en bytes de la clase representada por `td` .</span><span class="sxs-lookup"><span data-stu-id="ef7e3-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef7e3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef7e3-112">Requirements</span></span>  

 <span data-ttu-id="ef7e3-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef7e3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef7e3-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ef7e3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef7e3-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef7e3-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef7e3-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef7e3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7e3-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef7e3-117">See also</span></span>

- [<span data-ttu-id="ef7e3-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef7e3-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ef7e3-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef7e3-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
