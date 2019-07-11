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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8159b5245598993a2075fb402b280f9ab4cb2cfa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782459"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="60811-102">IMetaDataImport::FindTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="60811-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="60811-103">Obtiene un puntero al TypeRef token para el <xref:System.Type> referencia que se encuentra en el ámbito especificado y que tiene el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="60811-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60811-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60811-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60811-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60811-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="60811-106">[in] Un token ModuleRef, AssemblyRef o TypeRef que especifica el módulo, ensamblado o tipo, respectivamente, en que el tipo de referencia se define.</span><span class="sxs-lookup"><span data-stu-id="60811-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="60811-107">[in] El nombre de la referencia de tipo que se buscará.</span><span class="sxs-lookup"><span data-stu-id="60811-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="60811-108">[out] Un puntero al token TypeRef coincidente.</span><span class="sxs-lookup"><span data-stu-id="60811-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60811-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60811-109">Requirements</span></span>  
 <span data-ttu-id="60811-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60811-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60811-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="60811-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60811-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60811-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="60811-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60811-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60811-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="60811-114">See also</span></span>

- [<span data-ttu-id="60811-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60811-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="60811-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60811-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
