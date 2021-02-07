---
description: 'Más información sobre: IMetaDataImport:: Enummethods ((método)'
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
ms.openlocfilehash: 4fce3593d088a8d401335869eb49e598ac4c3fd2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670685"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="1073e-103">IMetaDataImport::EnumMethods (Método)</span><span class="sxs-lookup"><span data-stu-id="1073e-103">IMetaDataImport::EnumMethods Method</span></span>

<span data-ttu-id="1073e-104">Enumera los tokens de MethodDef que representan métodos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="1073e-104">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1073e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1073e-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1073e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1073e-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="1073e-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="1073e-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1073e-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="1073e-108">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="1073e-109">de Un token de TypeDef que representa el tipo con los métodos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="1073e-109">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="1073e-110">enuncia Matriz en la que se van a almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="1073e-110">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1073e-111">de Tamaño máximo de la matriz MethodDef `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="1073e-111">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1073e-112">enuncia Número de tokens de MethodDef devueltos en `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="1073e-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1073e-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1073e-113">Return Value</span></span>  
  
|<span data-ttu-id="1073e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1073e-114">HRESULT</span></span>|<span data-ttu-id="1073e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="1073e-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1073e-116">`EnumMethods` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1073e-116">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1073e-117">No hay tokens de MethodDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="1073e-117">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="1073e-118">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="1073e-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1073e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1073e-119">Requirements</span></span>  

 <span data-ttu-id="1073e-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1073e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1073e-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1073e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1073e-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1073e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1073e-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1073e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1073e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1073e-124">See also</span></span>

- [<span data-ttu-id="1073e-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1073e-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1073e-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1073e-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
