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
ms.openlocfilehash: 6462496a8804d9aa5304107a6c01122b745038fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500257"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="b114c-102">IMetaDataImport::GetNestedClassProps (Método)</span><span class="sxs-lookup"><span data-stu-id="b114c-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="b114c-103">Obtiene la definición de tipo (token) para el elemento primario <xref:System.Type> del elemento especificado de tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="b114c-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b114c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b114c-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b114c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b114c-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="b114c-106">[in] Una definición de tipo token que representa el <xref:System.Type> para devolver la clase primaria símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="b114c-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="b114c-107">[out] Un puntero al token de TypeDef para el <xref:System.Type> que `tdNestedClass` está anidado en.</span><span class="sxs-lookup"><span data-stu-id="b114c-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b114c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b114c-108">Requirements</span></span>  
 <span data-ttu-id="b114c-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b114c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b114c-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b114c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b114c-111">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b114c-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b114c-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b114c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b114c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b114c-113">See also</span></span>
- [<span data-ttu-id="b114c-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b114c-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b114c-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b114c-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
