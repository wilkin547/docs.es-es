---
description: 'Más información acerca de: IMetaDataEmit::D método efinePinvokeMap'
title: IMetaDataEmit::DefinePinvokeMap (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: 7b0477ca603241e773a67f335da579daa2ed3d30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784072"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="ab930-103">IMetaDataEmit::DefinePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="ab930-103">IMetaDataEmit::DefinePinvokeMap Method</span></span>

<span data-ttu-id="ab930-104">Establece las características de la firma PInvoke del método al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="ab930-104">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab930-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab930-105">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab930-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab930-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="ab930-107">de Token del método de destino.</span><span class="sxs-lookup"><span data-stu-id="ab930-107">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="ab930-108">de Marcas usadas por PInvoke para realizar la asignación.</span><span class="sxs-lookup"><span data-stu-id="ab930-108">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="ab930-109">de Nombre del método de exportación de destino en un archivo DLL no administrado.</span><span class="sxs-lookup"><span data-stu-id="ab930-109">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="ab930-110">de El token para la DLL nativa de destino.</span><span class="sxs-lookup"><span data-stu-id="ab930-110">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab930-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab930-111">Requirements</span></span>  

 <span data-ttu-id="ab930-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab930-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab930-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ab930-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab930-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab930-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab930-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab930-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab930-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab930-116">See also</span></span>

- [<span data-ttu-id="ab930-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab930-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ab930-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab930-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
