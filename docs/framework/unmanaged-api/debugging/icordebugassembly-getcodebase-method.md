---
description: 'Más información acerca de: ICorDebugAssembly:: getCodeBase ((método)'
title: ICorDebugAssembly::GetCodeBase (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetCodeBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetCodeBase
helpviewer_keywords:
- GetCodeBase method [.NET Framework debugging]
- ICorDebugAssembly::GetCodeBase method [.NET Framework debugging]
ms.assetid: 48adc154-9058-4fef-9c43-e9aad80e4dbf
topic_type:
- apiref
ms.openlocfilehash: 9774ffe69089305909aab68f2164bfd9e59b3e94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711965"
---
# <a name="icordebugassemblygetcodebase-method"></a><span data-ttu-id="1bd97-103">ICorDebugAssembly::GetCodeBase (Método)</span><span class="sxs-lookup"><span data-stu-id="1bd97-103">ICorDebugAssembly::GetCodeBase Method</span></span>

<span data-ttu-id="1bd97-104">Este método no está implementado en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1bd97-104">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd97-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bd97-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeBase (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR szName[]  
);  
```
