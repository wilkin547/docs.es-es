---
description: 'Más información sobre: IMetaDataImport:: Findtyperef ((método)'
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
ms.openlocfilehash: 11e966256b5e75c1acff0bf1e6de0c96dc03e6aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745572"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="d0259-103">IMetaDataImport::FindTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="d0259-103">IMetaDataImport::FindTypeRef Method</span></span>

<span data-ttu-id="d0259-104">Obtiene un puntero al token TypeRef para la <xref:System.Type> referencia que está en el ámbito especificado y que tiene el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="d0259-104">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0259-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0259-105">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0259-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0259-106">Parameters</span></span>  

 `tkResolutionScope`  
 <span data-ttu-id="d0259-107">de Un token ModuleRef, AssemblyRef o TypeRef que especifica el módulo, el ensamblado o el tipo, respectivamente, en el que se define la referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="d0259-107">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="d0259-108">de Nombre de la referencia de tipo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="d0259-108">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="d0259-109">enuncia Puntero al token TypeRef coincidente.</span><span class="sxs-lookup"><span data-stu-id="d0259-109">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0259-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0259-110">Requirements</span></span>  

 <span data-ttu-id="d0259-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0259-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0259-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d0259-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0259-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0259-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0259-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0259-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0259-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0259-115">See also</span></span>

- [<span data-ttu-id="d0259-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0259-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d0259-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0259-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
