---
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
ms.openlocfilehash: 193e8788d5a1b28f43f2fb0d4d935a18542dd923
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427494"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="18cb0-102">IMetaDataImport::EnumMethodImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="18cb0-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="18cb0-103">Enumera los tokens MethodBody y MethodDeclaration que representan métodos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="18cb0-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18cb0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18cb0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="18cb0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="18cb0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="18cb0-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="18cb0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="18cb0-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="18cb0-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="18cb0-108">de Un token de TypeDef para el tipo cuyas implementaciones de método se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="18cb0-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="18cb0-109">enuncia Matriz en la que se van a almacenar los tokens de MethodBody.</span><span class="sxs-lookup"><span data-stu-id="18cb0-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="18cb0-110">enuncia Matriz en la que se van a almacenar los tokens MethodDeclaration.</span><span class="sxs-lookup"><span data-stu-id="18cb0-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="18cb0-111">de Tamaño máximo de las matrices de `rMethodBody` y `rMethodDecl`.</span><span class="sxs-lookup"><span data-stu-id="18cb0-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="18cb0-112">de Número real de métodos devueltos en `rMethodBody` y `rMethodDecl`.</span><span class="sxs-lookup"><span data-stu-id="18cb0-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18cb0-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="18cb0-113">Return Value</span></span>  
  
|<span data-ttu-id="18cb0-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18cb0-114">HRESULT</span></span>|<span data-ttu-id="18cb0-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="18cb0-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="18cb0-116">`EnumMethodImpls` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="18cb0-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="18cb0-117">No hay tokens de método para enumerar.</span><span class="sxs-lookup"><span data-stu-id="18cb0-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="18cb0-118">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="18cb0-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18cb0-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18cb0-119">Requirements</span></span>  
 <span data-ttu-id="18cb0-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18cb0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18cb0-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="18cb0-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18cb0-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="18cb0-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18cb0-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18cb0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18cb0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="18cb0-124">See also</span></span>

- [<span data-ttu-id="18cb0-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="18cb0-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="18cb0-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="18cb0-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
