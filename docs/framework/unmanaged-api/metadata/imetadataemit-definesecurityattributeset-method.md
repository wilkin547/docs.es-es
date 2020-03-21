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
ms.openlocfilehash: fadd1974cd4fa8a51a06700835f46df24e37d7fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175777"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="26745-102">IMetaDataEmit::DefineSecurityAttributeSet (Método)</span><span class="sxs-lookup"><span data-stu-id="26745-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="26745-103">Crea un conjunto de permisos de seguridad para adjuntar al objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="26745-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26745-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26745-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26745-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26745-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="26745-106">[en] El token al que se adjunta la información de seguridad.</span><span class="sxs-lookup"><span data-stu-id="26745-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="26745-107">[en] Una matriz `COR_SECATTR` de estructuras.</span><span class="sxs-lookup"><span data-stu-id="26745-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="26745-108">[en] El número de `rSecAttrs`elementos en .</span><span class="sxs-lookup"><span data-stu-id="26745-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="26745-109">[fuera] Si se produce un error `rSecAttrs` en el método, especifica el índice en del elemento que causó el problema.</span><span class="sxs-lookup"><span data-stu-id="26745-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26745-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26745-110">Requirements</span></span>  
 <span data-ttu-id="26745-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26745-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26745-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="26745-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26745-113">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26745-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26745-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26745-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26745-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26745-115">See also</span></span>

- [<span data-ttu-id="26745-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="26745-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="26745-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="26745-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
