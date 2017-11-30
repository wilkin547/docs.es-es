---
title: "ICorDebugType::GetBase (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetBase
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de00e519b43d486e70d5ed8165eed01b59d6e725
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="bfd4d-102">ICorDebugType::GetBase (Método)</span><span class="sxs-lookup"><span data-stu-id="bfd4d-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="bfd4d-103">Obtiene un puntero de interfaz a una instancia de ICorDebugType que representa el tipo base, si existe, del tipo representado por este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="bfd4d-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfd4d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfd4d-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfd4d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bfd4d-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="bfd4d-106">[out] Un puntero a la dirección de un `ICorDebugType` objeto que representa el tipo base.</span><span class="sxs-lookup"><span data-stu-id="bfd4d-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfd4d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfd4d-107">Remarks</span></span>  
 <span data-ttu-id="bfd4d-108">Buscar el tipo base para un tipo es útil para implementar funciones de depuración comunes, como imprimir todos los campos de un objeto o sus clases primarias.</span><span class="sxs-lookup"><span data-stu-id="bfd4d-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfd4d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfd4d-109">Requirements</span></span>  
 <span data-ttu-id="bfd4d-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfd4d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfd4d-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfd4d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfd4d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfd4d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfd4d-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfd4d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
