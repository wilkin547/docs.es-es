---
description: 'Más información sobre: IMetaDataImport:: Getnestedclassprops ((método)'
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
ms.openlocfilehash: 5fd812bf9b7725d520b14284db400bb50e82c25b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677544"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="a5b64-103">IMetaDataImport::GetNestedClassProps (Método)</span><span class="sxs-lookup"><span data-stu-id="a5b64-103">IMetaDataImport::GetNestedClassProps Method</span></span>

<span data-ttu-id="a5b64-104">Obtiene el token de TypeDef para el elemento primario <xref:System.Type> del tipo anidado especificado.</span><span class="sxs-lookup"><span data-stu-id="a5b64-104">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5b64-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5b64-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5b64-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5b64-106">Parameters</span></span>  

 `tdNestedClass`  
 <span data-ttu-id="a5b64-107">de Un token de TypeDef que representa el <xref:System.Type> para el que se va a devolver el token de clase principal.</span><span class="sxs-lookup"><span data-stu-id="a5b64-107">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="a5b64-108">enuncia Puntero al token de TypeDef para el <xref:System.Type> que `tdNestedClass` está anidado en.</span><span class="sxs-lookup"><span data-stu-id="a5b64-108">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5b64-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5b64-109">Requirements</span></span>  

 <span data-ttu-id="a5b64-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5b64-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5b64-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a5b64-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5b64-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5b64-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5b64-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5b64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b64-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5b64-114">See also</span></span>

- [<span data-ttu-id="a5b64-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5b64-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a5b64-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5b64-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
