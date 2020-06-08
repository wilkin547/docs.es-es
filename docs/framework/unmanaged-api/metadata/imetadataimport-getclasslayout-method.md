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
ms.openlocfilehash: 36c0ffef2d984604be4ae19899e8f3f912cee123
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491477"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="d7e84-102">IMetaDataImport::GetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="d7e84-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="d7e84-103">Obtiene la información de diseño de la clase a la que hace referencia el token TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="d7e84-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7e84-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d7e84-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7e84-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d7e84-106">de El token de TypeDef para la clase con el diseño que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="d7e84-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="d7e84-107">enuncia Uno de los valores 1, 2, 4, 8 o 16 que representa el tamaño de paquete de la clase.</span><span class="sxs-lookup"><span data-stu-id="d7e84-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="d7e84-108">enuncia Matriz de valores de [COR_FIELD_OFFSET](cor-field-offset-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d7e84-108">[out] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d7e84-109">[in] Tamaño máximo de la matriz `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="d7e84-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="d7e84-110">enuncia Número de elementos devueltos en `rFieldOffset` .</span><span class="sxs-lookup"><span data-stu-id="d7e84-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="d7e84-111">enuncia Tamaño en bytes de la clase representada por `td` .</span><span class="sxs-lookup"><span data-stu-id="d7e84-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7e84-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7e84-112">Requirements</span></span>  
 <span data-ttu-id="d7e84-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7e84-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7e84-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d7e84-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7e84-115">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d7e84-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7e84-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7e84-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e84-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="d7e84-117">See also</span></span>

- [<span data-ttu-id="d7e84-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7e84-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d7e84-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7e84-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
