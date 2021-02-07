---
description: 'Más información acerca de: IMetaDataImport:: GetClassLayout (método)'
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
ms.openlocfilehash: 74a3170e40a7f857b9150f2d0048af3eac0f2cbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745429"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="5dffe-103">IMetaDataImport::GetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="5dffe-103">IMetaDataImport::GetClassLayout Method</span></span>

<span data-ttu-id="5dffe-104">Obtiene la información de diseño de la clase a la que hace referencia el token TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="5dffe-104">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dffe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5dffe-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5dffe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5dffe-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="5dffe-107">de El token de TypeDef para la clase con el diseño que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="5dffe-107">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="5dffe-108">enuncia Uno de los valores 1, 2, 4, 8 o 16 que representa el tamaño de paquete de la clase.</span><span class="sxs-lookup"><span data-stu-id="5dffe-108">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="5dffe-109">enuncia Matriz de valores de [COR_FIELD_OFFSET](cor-field-offset-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="5dffe-109">[out] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5dffe-110">[in] Tamaño máximo de la matriz `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="5dffe-110">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="5dffe-111">enuncia Número de elementos devueltos en `rFieldOffset` .</span><span class="sxs-lookup"><span data-stu-id="5dffe-111">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="5dffe-112">enuncia Tamaño en bytes de la clase representada por `td` .</span><span class="sxs-lookup"><span data-stu-id="5dffe-112">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dffe-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5dffe-113">Requirements</span></span>  

 <span data-ttu-id="5dffe-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dffe-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dffe-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5dffe-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5dffe-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5dffe-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5dffe-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dffe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dffe-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dffe-118">See also</span></span>

- [<span data-ttu-id="5dffe-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5dffe-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5dffe-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5dffe-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
