---
description: 'Más información sobre: IMetaDataImport:: Enummethodimpls ((método)'
title: IMetaDataImport::EnumMethodImpls (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: 3ae5795bdde36ad07c447370553e24e1ceacf493
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670702"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="1ffaa-103">IMetaDataImport::EnumMethodImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="1ffaa-103">IMetaDataImport::EnumMethodImpls Method</span></span>

<span data-ttu-id="1ffaa-104">Enumera los tokens MethodBody y MethodDeclaration que representan métodos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="1ffaa-104">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ffaa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ffaa-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ffaa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ffaa-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="1ffaa-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="1ffaa-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1ffaa-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="1ffaa-108">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="1ffaa-109">de Un token de TypeDef para el tipo cuyas implementaciones de método se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="1ffaa-109">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="1ffaa-110">enuncia Matriz en la que se van a almacenar los tokens de MethodBody.</span><span class="sxs-lookup"><span data-stu-id="1ffaa-110">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="1ffaa-111">enuncia Matriz en la que se van a almacenar los tokens MethodDeclaration.</span><span class="sxs-lookup"><span data-stu-id="1ffaa-111">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1ffaa-112">de Tamaño máximo de las `rMethodBody` matrices y `rMethodDecl` .</span><span class="sxs-lookup"><span data-stu-id="1ffaa-112">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1ffaa-113">de Número real de métodos devueltos en `rMethodBody` y `rMethodDecl` .</span><span class="sxs-lookup"><span data-stu-id="1ffaa-113">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ffaa-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ffaa-114">Return Value</span></span>  
  
|<span data-ttu-id="1ffaa-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ffaa-115">HRESULT</span></span>|<span data-ttu-id="1ffaa-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ffaa-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1ffaa-117">`EnumMethodImpls` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ffaa-117">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1ffaa-118">No hay tokens de método para enumerar.</span><span class="sxs-lookup"><span data-stu-id="1ffaa-118">There are no method tokens to enumerate.</span></span> <span data-ttu-id="1ffaa-119">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="1ffaa-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ffaa-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ffaa-120">Requirements</span></span>  

 <span data-ttu-id="1ffaa-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ffaa-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ffaa-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1ffaa-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ffaa-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ffaa-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ffaa-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ffaa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ffaa-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ffaa-125">See also</span></span>

- [<span data-ttu-id="1ffaa-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ffaa-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1ffaa-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ffaa-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
