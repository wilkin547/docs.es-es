---
title: IMetaDataImport2::EnumGenericParams (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7edd2eeafcce6a22c3256d0684a9c4f961b34002
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157643"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="76af4-102">IMetaDataImport2::EnumGenericParams (Método)</span><span class="sxs-lookup"><span data-stu-id="76af4-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="76af4-103">Obtiene un enumerador para una matriz de los tokens de parámetro genérico asociado con la definición de tipo especificado o MethodDef (token).</span><span class="sxs-lookup"><span data-stu-id="76af4-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76af4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76af4-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76af4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76af4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="76af4-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="76af4-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="76af4-107">[in] El token de TypeDef o MethodDef cuyos parámetros genéricos son que hay que enumerar.</span><span class="sxs-lookup"><span data-stu-id="76af4-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="76af4-108">[out] Matriz de parámetros genéricos a enumerar.</span><span class="sxs-lookup"><span data-stu-id="76af4-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="76af4-109">[in] El número máximo solicitado de tokens para colocar en `rGenericParams`.</span><span class="sxs-lookup"><span data-stu-id="76af4-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="76af4-110">[out] El número de símbolos (token) devuelto se coloca en `rGenericParams`.</span><span class="sxs-lookup"><span data-stu-id="76af4-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76af4-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76af4-111">Return Value</span></span>  
  
|<span data-ttu-id="76af4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76af4-112">HRESULT</span></span>|<span data-ttu-id="76af4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="76af4-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParams` <span data-ttu-id="76af4-114">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="76af4-114">returned successfully.</span></span>|  
|`S_FALSE`|`phEnum` <span data-ttu-id="76af4-115">no tiene ningún elemento de miembro.</span><span class="sxs-lookup"><span data-stu-id="76af4-115">has no member elements.</span></span> <span data-ttu-id="76af4-116">En este caso, `pcGenericParams` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="76af4-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76af4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76af4-117">Requirements</span></span>  
 <span data-ttu-id="76af4-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76af4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76af4-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="76af4-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76af4-120">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76af4-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="76af4-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="76af4-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="76af4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="76af4-122">See also</span></span>

- [<span data-ttu-id="76af4-123">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76af4-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="76af4-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76af4-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
