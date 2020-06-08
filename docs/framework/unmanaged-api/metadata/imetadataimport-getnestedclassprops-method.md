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
ms.openlocfilehash: 82cf5e14520f0e677c2d274cf013d8a0020e8fa2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503541"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="f4992-102">IMetaDataImport::GetNestedClassProps (Método)</span><span class="sxs-lookup"><span data-stu-id="f4992-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="f4992-103">Obtiene el token de TypeDef para el elemento primario <xref:System.Type> del tipo anidado especificado.</span><span class="sxs-lookup"><span data-stu-id="f4992-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4992-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4992-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4992-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4992-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="f4992-106">de Un token de TypeDef que representa el <xref:System.Type> para el que se va a devolver el token de clase principal.</span><span class="sxs-lookup"><span data-stu-id="f4992-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="f4992-107">enuncia Puntero al token de TypeDef para el <xref:System.Type> que `tdNestedClass` está anidado en.</span><span class="sxs-lookup"><span data-stu-id="f4992-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4992-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4992-108">Requirements</span></span>  
 <span data-ttu-id="f4992-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4992-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4992-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f4992-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4992-111">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f4992-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4992-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4992-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4992-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f4992-113">See also</span></span>

- [<span data-ttu-id="f4992-114">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4992-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f4992-115">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4992-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
