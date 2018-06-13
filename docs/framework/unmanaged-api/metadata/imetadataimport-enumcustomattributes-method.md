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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b549c6eacad63b165d26c203817f1a2adac57bca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448643"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="a7974-102">IMetaDataImport::EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="a7974-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="a7974-103">Enumera los tokens de definición de atributos personalizados asociados con el tipo o miembro especificado.</span><span class="sxs-lookup"><span data-stu-id="a7974-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7974-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7974-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7974-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7974-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a7974-106">[entrada, salida] Un puntero al enumerador devuelto.</span><span class="sxs-lookup"><span data-stu-id="a7974-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="a7974-107">[in] Un token para el ámbito de la enumeración, o cero para todos los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a7974-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="a7974-108">[in] Un token para el constructor del tipo de los atributos que se van a enumerar, o `null` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="a7974-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="a7974-109">[out] Una matriz de símbolos (tokens) de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a7974-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a7974-110">[in] Tamaño máximo de la matriz `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="a7974-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="a7974-111">[out, optional] El número real de valores de símbolo (token) devueltos por `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="a7974-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7974-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a7974-112">Return Value</span></span>  
  
|<span data-ttu-id="a7974-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7974-113">HRESULT</span></span>|<span data-ttu-id="a7974-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7974-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a7974-115">`EnumCustomAttributes` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7974-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a7974-116">No hay ningún atributo personalizado para enumerar.</span><span class="sxs-lookup"><span data-stu-id="a7974-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="a7974-117">En ese caso, `pcCustomAttributes` es cero.</span><span class="sxs-lookup"><span data-stu-id="a7974-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7974-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7974-118">Requirements</span></span>  
 <span data-ttu-id="a7974-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7974-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7974-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7974-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7974-121">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7974-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7974-122">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7974-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7974-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7974-123">See Also</span></span>  
 [<span data-ttu-id="a7974-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7974-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a7974-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7974-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
