---
description: 'Más información sobre: IMetaDataImport:: Enumcustomattributes ((método)'
title: IMetaDataImport::EnumCustomAttributes (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: 1c55ea4b72483e5dc30425172b95be7f77e8a62a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677592"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="78cef-103">IMetaDataImport::EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="78cef-103">IMetaDataImport::EnumCustomAttributes Method</span></span>

<span data-ttu-id="78cef-104">Enumera los tokens de definición de atributos personalizados asociados al tipo o miembro especificado.</span><span class="sxs-lookup"><span data-stu-id="78cef-104">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78cef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78cef-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78cef-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78cef-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="78cef-107">[in, out] Puntero al enumerador devuelto.</span><span class="sxs-lookup"><span data-stu-id="78cef-107">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="78cef-108">de Un token para el ámbito de la enumeración o cero para todos los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="78cef-108">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="78cef-109">de Token para el constructor del tipo de los atributos que se van a enumerar o `null` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="78cef-109">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="78cef-110">enuncia Matriz de tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="78cef-110">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="78cef-111">[in] Tamaño máximo de la matriz `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="78cef-111">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="78cef-112">[out, opcional] Número real de valores de token devueltos en `rCustomAttributes` .</span><span class="sxs-lookup"><span data-stu-id="78cef-112">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78cef-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="78cef-113">Return Value</span></span>  
  
|<span data-ttu-id="78cef-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78cef-114">HRESULT</span></span>|<span data-ttu-id="78cef-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="78cef-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="78cef-116">`EnumCustomAttributes` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="78cef-116">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="78cef-117">No hay atributos personalizados para enumerar.</span><span class="sxs-lookup"><span data-stu-id="78cef-117">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="78cef-118">En ese caso, `pcCustomAttributes` es cero.</span><span class="sxs-lookup"><span data-stu-id="78cef-118">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78cef-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78cef-119">Requirements</span></span>  

 <span data-ttu-id="78cef-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78cef-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78cef-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="78cef-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78cef-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78cef-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78cef-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78cef-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78cef-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="78cef-124">See also</span></span>

- [<span data-ttu-id="78cef-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="78cef-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="78cef-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="78cef-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
