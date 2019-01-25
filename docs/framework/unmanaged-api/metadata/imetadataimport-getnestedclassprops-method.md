---
title: IMetaDataImport::GetNestedClassProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9e54b4c4b1b3184b6aa0d50f82a501312db6a8e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655666"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="940a3-102">IMetaDataImport::GetNestedClassProps (Método)</span><span class="sxs-lookup"><span data-stu-id="940a3-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="940a3-103">Obtiene la definición de tipo (token) para el elemento primario <xref:System.Type> del elemento especificado de tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="940a3-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="940a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="940a3-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="940a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="940a3-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="940a3-106">[in] Una definición de tipo token que representa el <xref:System.Type> para devolver la clase primaria símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="940a3-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="940a3-107">[out] Un puntero al token de TypeDef para el <xref:System.Type> que `tdNestedClass` está anidado en.</span><span class="sxs-lookup"><span data-stu-id="940a3-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="940a3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="940a3-108">Requirements</span></span>  
 <span data-ttu-id="940a3-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="940a3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="940a3-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="940a3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="940a3-111">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="940a3-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="940a3-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="940a3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940a3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="940a3-113">See also</span></span>
- [<span data-ttu-id="940a3-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="940a3-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="940a3-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="940a3-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
