---
description: 'Más información acerca de: ICorDebugModule:: GetToken (método)'
title: ICorDebugModule::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: fd1bc4bc397e7f81c77f2fe784c68dbaaceb2695
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660172"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="fe465-103">ICorDebugModule::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="fe465-103">ICorDebugModule::GetToken Method</span></span>

<span data-ttu-id="fe465-104">Obtiene el token para la entrada de la tabla para este módulo.</span><span class="sxs-lookup"><span data-stu-id="fe465-104">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe465-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe465-105">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe465-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe465-106">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="fe465-107">enuncia Puntero al `mdModule` token que hace referencia a los metadatos del módulo.</span><span class="sxs-lookup"><span data-stu-id="fe465-107">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe465-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fe465-108">Remarks</span></span>  

 <span data-ttu-id="fe465-109">El token se puede pasar a las interfaces de importación de metadatos [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md)y [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fe465-109">The token can be passed to the [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe465-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe465-110">Requirements</span></span>  

 <span data-ttu-id="fe465-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe465-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe465-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe465-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe465-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe465-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe465-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe465-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe465-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe465-115">See also</span></span>

- [<span data-ttu-id="fe465-116">Metadata</span><span class="sxs-lookup"><span data-stu-id="fe465-116">Metadata</span></span>](../metadata/index.md)
