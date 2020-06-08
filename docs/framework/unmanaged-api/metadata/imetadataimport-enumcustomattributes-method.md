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
ms.openlocfilehash: 9b0da8a06259fe99da52497da3011da94289d301
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492335"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="14481-102">IMetaDataImport::EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="14481-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="14481-103">Enumera los tokens de definición de atributos personalizados asociados al tipo o miembro especificado.</span><span class="sxs-lookup"><span data-stu-id="14481-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14481-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14481-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="14481-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14481-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="14481-106">[in, out] Puntero al enumerador devuelto.</span><span class="sxs-lookup"><span data-stu-id="14481-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="14481-107">de Un token para el ámbito de la enumeración o cero para todos los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="14481-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="14481-108">de Token para el constructor del tipo de los atributos que se van a enumerar o `null` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="14481-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="14481-109">enuncia Matriz de tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="14481-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="14481-110">[in] Tamaño máximo de la matriz `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="14481-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="14481-111">[out, opcional] Número real de valores de token devueltos en `rCustomAttributes` .</span><span class="sxs-lookup"><span data-stu-id="14481-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14481-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="14481-112">Return Value</span></span>  
  
|<span data-ttu-id="14481-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14481-113">HRESULT</span></span>|<span data-ttu-id="14481-114">Description</span><span class="sxs-lookup"><span data-stu-id="14481-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="14481-115">`EnumCustomAttributes`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="14481-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="14481-116">No hay atributos personalizados para enumerar.</span><span class="sxs-lookup"><span data-stu-id="14481-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="14481-117">En ese caso, `pcCustomAttributes` es cero.</span><span class="sxs-lookup"><span data-stu-id="14481-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14481-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14481-118">Requirements</span></span>  
 <span data-ttu-id="14481-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14481-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14481-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="14481-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="14481-121">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="14481-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="14481-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14481-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14481-123">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="14481-123">See also</span></span>

- [<span data-ttu-id="14481-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14481-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="14481-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14481-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
