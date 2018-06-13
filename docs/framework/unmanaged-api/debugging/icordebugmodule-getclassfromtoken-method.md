---
title: ICorDebugModule::GetClassFromToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 195cea23313d88b636479147faa512889ca94b17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413977"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="df22f-102">ICorDebugModule::GetClassFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="df22f-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="df22f-103">Obtiene la clase especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="df22f-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df22f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df22f-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df22f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df22f-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="df22f-106">[in] Un `mdTypeDef` símbolo (token) de metadatos que hace referencia a los metadatos de una clase.</span><span class="sxs-lookup"><span data-stu-id="df22f-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="df22f-107">[out] Un puntero a la dirección de un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="df22f-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df22f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df22f-108">Requirements</span></span>  
 <span data-ttu-id="df22f-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df22f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df22f-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df22f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df22f-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df22f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df22f-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df22f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
