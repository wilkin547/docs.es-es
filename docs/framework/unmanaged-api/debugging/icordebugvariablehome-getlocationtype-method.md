---
title: Método ICorDebugVariableHome::GetLocationType
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af879cbbf8edfd05e79d9b77b0c1fb71b2c835c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224304"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="b7f56-102">Método ICorDebugVariableHome::GetLocationType</span><span class="sxs-lookup"><span data-stu-id="b7f56-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="b7f56-103">Obtiene el tipo de ubicación de la variable nativa.</span><span class="sxs-lookup"><span data-stu-id="b7f56-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7f56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7f56-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7f56-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7f56-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="b7f56-106">[out] Un puntero al tipo de ubicación de la variable nativa.</span><span class="sxs-lookup"><span data-stu-id="b7f56-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="b7f56-107">Consulte la [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeración para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b7f56-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7f56-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7f56-108">Requirements</span></span>  
 <span data-ttu-id="b7f56-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7f56-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7f56-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7f56-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7f56-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7f56-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b7f56-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b7f56-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7f56-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7f56-113">See also</span></span>

- [<span data-ttu-id="b7f56-114">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="b7f56-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="b7f56-115">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="b7f56-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
