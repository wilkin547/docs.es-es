---
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
ms.openlocfilehash: 61b5678a546bdbadbcc6d8ee86447cb17ce72b99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175530"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="bebfb-102">IMetaDataImport::EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="bebfb-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="bebfb-103">Enumera los tokens de definición de atributos personalizados asociados con el tipo o miembro especificado.</span><span class="sxs-lookup"><span data-stu-id="bebfb-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bebfb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bebfb-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bebfb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bebfb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bebfb-106">[adentro, fuera] Un puntero al enumerador devuelto.</span><span class="sxs-lookup"><span data-stu-id="bebfb-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="bebfb-107">[en] Un token para el ámbito de la enumeración, o cero para todos los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="bebfb-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="bebfb-108">[en] Un token para el constructor del tipo de los `null` atributos que se van a enumerar, o para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="bebfb-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="bebfb-109">[fuera] Matriz de tokens de atributo personalizados.</span><span class="sxs-lookup"><span data-stu-id="bebfb-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bebfb-110">[in] Tamaño máximo de la matriz `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="bebfb-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="bebfb-111">[fuera, opcional] El número real de `rCustomAttributes`valores de token devueltos en .</span><span class="sxs-lookup"><span data-stu-id="bebfb-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bebfb-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bebfb-112">Return Value</span></span>  
  
|<span data-ttu-id="bebfb-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bebfb-113">HRESULT</span></span>|<span data-ttu-id="bebfb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bebfb-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bebfb-115">`EnumCustomAttributes`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="bebfb-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bebfb-116">No hay atributos personalizados para enumerar.</span><span class="sxs-lookup"><span data-stu-id="bebfb-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="bebfb-117">En ese `pcCustomAttributes` caso, es cero.</span><span class="sxs-lookup"><span data-stu-id="bebfb-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bebfb-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bebfb-118">Requirements</span></span>  
 <span data-ttu-id="bebfb-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bebfb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bebfb-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bebfb-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bebfb-121">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bebfb-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bebfb-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bebfb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bebfb-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bebfb-123">See also</span></span>

- [<span data-ttu-id="bebfb-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bebfb-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bebfb-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bebfb-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
