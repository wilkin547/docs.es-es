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
ms.openlocfilehash: 0adf4f91e1bc7bfb72f634cb3bf038710198b74f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437143"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="53b0b-102">IMetaDataImport::GetNestedClassProps (Método)</span><span class="sxs-lookup"><span data-stu-id="53b0b-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="53b0b-103">Obtiene el token de TypeDef para el <xref:System.Type> primario del tipo anidado especificado.</span><span class="sxs-lookup"><span data-stu-id="53b0b-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53b0b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53b0b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53b0b-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="53b0b-106">de Un token de TypeDef que representa la <xref:System.Type> para la que se va a devolver el token de clase principal.</span><span class="sxs-lookup"><span data-stu-id="53b0b-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="53b0b-107">enuncia Puntero al token de TypeDef para el <xref:System.Type> en el que está anidado `tdNestedClass`.</span><span class="sxs-lookup"><span data-stu-id="53b0b-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53b0b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53b0b-108">Requirements</span></span>  
 <span data-ttu-id="53b0b-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53b0b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53b0b-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="53b0b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53b0b-111">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="53b0b-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53b0b-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53b0b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b0b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="53b0b-113">See also</span></span>

- [<span data-ttu-id="53b0b-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53b0b-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="53b0b-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53b0b-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
