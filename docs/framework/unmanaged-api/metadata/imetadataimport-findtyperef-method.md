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
ms.openlocfilehash: 3c96a9b601824cc4001568c4656f968fad70cf39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711291"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="b5a87-102">IMetaDataImport::FindTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="b5a87-102">IMetaDataImport::FindTypeRef Method</span></span>

<span data-ttu-id="b5a87-103">Obtiene un puntero al token TypeRef para la <xref:System.Type> referencia que está en el ámbito especificado y que tiene el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="b5a87-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5a87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5a87-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5a87-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5a87-105">Parameters</span></span>  

 `tkResolutionScope`  
 <span data-ttu-id="b5a87-106">de Un token ModuleRef, AssemblyRef o TypeRef que especifica el módulo, el ensamblado o el tipo, respectivamente, en el que se define la referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="b5a87-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="b5a87-107">de Nombre de la referencia de tipo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="b5a87-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="b5a87-108">enuncia Puntero al token TypeRef coincidente.</span><span class="sxs-lookup"><span data-stu-id="b5a87-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5a87-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5a87-109">Requirements</span></span>  

 <span data-ttu-id="b5a87-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5a87-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5a87-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b5a87-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5a87-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5a87-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5a87-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5a87-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a87-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5a87-114">See also</span></span>

- [<span data-ttu-id="b5a87-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5a87-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b5a87-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5a87-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
