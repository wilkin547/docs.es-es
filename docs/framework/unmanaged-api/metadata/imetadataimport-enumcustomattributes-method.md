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
ms.openlocfilehash: c38b7f060c34f7408195484dec2c49305db422fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781319"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="a7ad0-102">IMetaDataImport::EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="a7ad0-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="a7ad0-103">Enumera los tokens de definición de atributos personalizados asociados con el tipo o miembro especificado.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ad0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7ad0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a7ad0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7ad0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a7ad0-106">[in, out] Un puntero al enumerador devuelto.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="a7ad0-107">[in] Un token para el ámbito de la enumeración, o cero para todos los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="a7ad0-108">[in] Un token para el constructor del tipo de los atributos que se van a enumerar o `null` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="a7ad0-109">[out] Una matriz de los tokens de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a7ad0-110">[in] Tamaño máximo de la matriz `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="a7ad0-111">[out, optional] El número real de los valores de token devuelto en `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7ad0-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a7ad0-112">Return Value</span></span>  
  
|<span data-ttu-id="a7ad0-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7ad0-113">HRESULT</span></span>|<span data-ttu-id="a7ad0-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a7ad0-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a7ad0-115">`EnumCustomAttributes` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a7ad0-116">No hay ningún atributo personalizado a enumerar.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="a7ad0-117">En ese caso, `pcCustomAttributes` es cero.</span><span class="sxs-lookup"><span data-stu-id="a7ad0-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7ad0-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7ad0-118">Requirements</span></span>  
 <span data-ttu-id="a7ad0-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7ad0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ad0-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7ad0-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7ad0-121">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7ad0-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7ad0-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ad0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ad0-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7ad0-123">See also</span></span>

- [<span data-ttu-id="a7ad0-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7ad0-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a7ad0-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7ad0-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
