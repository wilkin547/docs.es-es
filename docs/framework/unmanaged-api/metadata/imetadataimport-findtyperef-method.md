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
ms.openlocfilehash: 545fe1e1d9e641d2225ad92c11453558dc4b97d1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491503"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="12707-102">IMetaDataImport::FindTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="12707-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="12707-103">Obtiene un puntero al token TypeRef para la <xref:System.Type> referencia que está en el ámbito especificado y que tiene el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="12707-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12707-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12707-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12707-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="12707-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="12707-106">de Un token ModuleRef, AssemblyRef o TypeRef que especifica el módulo, el ensamblado o el tipo, respectivamente, en el que se define la referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="12707-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="12707-107">de Nombre de la referencia de tipo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="12707-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="12707-108">enuncia Puntero al token TypeRef coincidente.</span><span class="sxs-lookup"><span data-stu-id="12707-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12707-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12707-109">Requirements</span></span>  
 <span data-ttu-id="12707-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12707-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12707-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="12707-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12707-112">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="12707-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="12707-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12707-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12707-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="12707-114">See also</span></span>

- [<span data-ttu-id="12707-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="12707-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="12707-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="12707-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
