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
ms.openlocfilehash: b98fab6c6127c3f78151d3b84160d4ca0434b6cd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428246"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="57b84-102">IMetaDataEmit::DefineSecurityAttributeSet (Método)</span><span class="sxs-lookup"><span data-stu-id="57b84-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="57b84-103">Crea un conjunto de permisos de seguridad que se van a adjuntar al objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="57b84-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57b84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57b84-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57b84-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57b84-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="57b84-106">de El token al que se adjunta la información de seguridad.</span><span class="sxs-lookup"><span data-stu-id="57b84-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="57b84-107">de Matriz de estructuras de `COR_SECATTR`.</span><span class="sxs-lookup"><span data-stu-id="57b84-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="57b84-108">de Número de elementos de `rSecAttrs`.</span><span class="sxs-lookup"><span data-stu-id="57b84-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="57b84-109">enuncia Si se produce un error en el método, especifica el índice en `rSecAttrs` del elemento que causó el problema.</span><span class="sxs-lookup"><span data-stu-id="57b84-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57b84-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57b84-110">Requirements</span></span>  
 <span data-ttu-id="57b84-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57b84-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57b84-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="57b84-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57b84-113">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="57b84-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57b84-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57b84-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b84-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="57b84-115">See also</span></span>

- [<span data-ttu-id="57b84-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="57b84-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="57b84-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="57b84-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
