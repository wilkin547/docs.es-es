---
title: IMetaDataImport::EnumMethods (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 91ae326a89e463d26b39c1659d872130042557bf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492027"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="3fa3d-102">IMetaDataImport::EnumMethods (Método)</span><span class="sxs-lookup"><span data-stu-id="3fa3d-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="3fa3d-103">Enumera los tokens de MethodDef que representan métodos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="3fa3d-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fa3d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fa3d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fa3d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3fa3d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3fa3d-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="3fa3d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3fa3d-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="3fa3d-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="3fa3d-108">de Un token de TypeDef que representa el tipo con los métodos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="3fa3d-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="3fa3d-109">enuncia Matriz en la que se van a almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="3fa3d-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3fa3d-110">de Tamaño máximo de la matriz MethodDef `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="3fa3d-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3fa3d-111">enuncia Número de tokens de MethodDef devueltos en `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="3fa3d-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fa3d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3fa3d-112">Return Value</span></span>  
  
|<span data-ttu-id="3fa3d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fa3d-113">HRESULT</span></span>|<span data-ttu-id="3fa3d-114">Description</span><span class="sxs-lookup"><span data-stu-id="3fa3d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3fa3d-115">`EnumMethods`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3fa3d-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3fa3d-116">No hay tokens de MethodDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="3fa3d-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="3fa3d-117">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="3fa3d-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3fa3d-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3fa3d-118">Requirements</span></span>  
 <span data-ttu-id="3fa3d-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fa3d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fa3d-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3fa3d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3fa3d-121">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3fa3d-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3fa3d-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fa3d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa3d-123">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="3fa3d-123">See also</span></span>

- [<span data-ttu-id="3fa3d-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fa3d-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3fa3d-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fa3d-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
