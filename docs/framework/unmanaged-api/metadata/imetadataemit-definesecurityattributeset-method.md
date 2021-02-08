---
description: 'Más información acerca de: IMetaDataEmit::D método efineSecurityAttributeSet'
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
ms.openlocfilehash: 3512857ca23d65389b0e150bd24234d272ddd9b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784059"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="61115-103">IMetaDataEmit::DefineSecurityAttributeSet (Método)</span><span class="sxs-lookup"><span data-stu-id="61115-103">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>

<span data-ttu-id="61115-104">Crea un conjunto de permisos de seguridad que se van a adjuntar al objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="61115-104">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61115-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61115-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61115-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="61115-106">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="61115-107">de El token al que se adjunta la información de seguridad.</span><span class="sxs-lookup"><span data-stu-id="61115-107">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="61115-108">de Matriz de `COR_SECATTR` estructuras.</span><span class="sxs-lookup"><span data-stu-id="61115-108">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="61115-109">de Número de elementos de `rSecAttrs` .</span><span class="sxs-lookup"><span data-stu-id="61115-109">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="61115-110">enuncia Si se produce un error en el método, especifica el índice `rSecAttrs` del elemento que provocó el problema.</span><span class="sxs-lookup"><span data-stu-id="61115-110">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61115-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61115-111">Requirements</span></span>  

 <span data-ttu-id="61115-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61115-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61115-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="61115-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61115-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61115-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61115-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61115-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61115-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="61115-116">See also</span></span>

- [<span data-ttu-id="61115-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61115-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="61115-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61115-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
