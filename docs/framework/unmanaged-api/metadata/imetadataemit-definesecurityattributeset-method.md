---
title: IMetaDataEmit::DefineSecurityAttributeSet (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
ms.openlocfilehash: 5caf07414c9e64169f272eb11169c4d4ee399c6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719468"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="40227-102">IMetaDataEmit::DefineSecurityAttributeSet (Método)</span><span class="sxs-lookup"><span data-stu-id="40227-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>

<span data-ttu-id="40227-103">Crea un conjunto de permisos de seguridad que se van a adjuntar al objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="40227-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40227-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40227-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40227-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40227-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="40227-106">de El token al que se adjunta la información de seguridad.</span><span class="sxs-lookup"><span data-stu-id="40227-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="40227-107">de Matriz de `COR_SECATTR` estructuras.</span><span class="sxs-lookup"><span data-stu-id="40227-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="40227-108">de Número de elementos de `rSecAttrs` .</span><span class="sxs-lookup"><span data-stu-id="40227-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="40227-109">enuncia Si se produce un error en el método, especifica el índice `rSecAttrs` del elemento que provocó el problema.</span><span class="sxs-lookup"><span data-stu-id="40227-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40227-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40227-110">Requirements</span></span>  

 <span data-ttu-id="40227-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40227-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40227-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="40227-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40227-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40227-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40227-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40227-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40227-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40227-115">See also</span></span>

- [<span data-ttu-id="40227-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40227-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="40227-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40227-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
