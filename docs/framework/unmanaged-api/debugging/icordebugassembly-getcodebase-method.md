---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6236d6b5349a9c2a528a85559c0cbc02c8da381
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645492"
---
# <a name="icordebugassemblygetcodebase-method"></a><span data-ttu-id="776d3-102">ICorDebugAssembly::GetCodeBase (Método)</span><span class="sxs-lookup"><span data-stu-id="776d3-102">ICorDebugAssembly::GetCodeBase Method</span></span>
<span data-ttu-id="776d3-103">Este método no se implementa en la versión actual de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="776d3-103">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="776d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="776d3-104">Syntax</span></span>  
  
```  
HRESULT GetCodeBase (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR szName[]  
);  
```
