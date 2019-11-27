---
title: IMetaDataImport::FindTypeRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
ms.openlocfilehash: 21a69d120cc732ca6659f77abc9f8ea0c993271e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437785"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="70fd9-102">IMetaDataImport::FindTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="70fd9-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="70fd9-103">Obtiene un puntero al token TypeRef para la <xref:System.Type> referencia que se encuentra en el ámbito especificado y que tiene el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="70fd9-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70fd9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70fd9-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70fd9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70fd9-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="70fd9-106">de Un token ModuleRef, AssemblyRef o TypeRef que especifica el módulo, el ensamblado o el tipo, respectivamente, en el que se define la referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="70fd9-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="70fd9-107">de Nombre de la referencia de tipo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="70fd9-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="70fd9-108">enuncia Puntero al token TypeRef coincidente.</span><span class="sxs-lookup"><span data-stu-id="70fd9-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70fd9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70fd9-109">Requirements</span></span>  
 <span data-ttu-id="70fd9-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70fd9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70fd9-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="70fd9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70fd9-112">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="70fd9-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70fd9-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70fd9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70fd9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="70fd9-114">See also</span></span>

- [<span data-ttu-id="70fd9-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="70fd9-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="70fd9-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="70fd9-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
