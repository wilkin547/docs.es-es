---
title: "ISymUnmanagedVariable::GetStartOffset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetStartOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3fa0c710eb5de8b9a92970002336de22adb2458
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="39af7-102">ISymUnmanagedVariable::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="39af7-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="39af7-103">Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="39af7-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="39af7-104">Si se trata de una variable local dentro de un ámbito, el desplazamiento inicial se encontrará dentro de los desplazamientos definidos para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="39af7-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39af7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39af7-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39af7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39af7-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="39af7-107">[out] Un puntero a un `ULONG32` que recibe el desplazamiento inicial.</span><span class="sxs-lookup"><span data-stu-id="39af7-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39af7-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="39af7-108">Return Value</span></span>  
 <span data-ttu-id="39af7-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="39af7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39af7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39af7-110">Requirements</span></span>  
 <span data-ttu-id="39af7-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="39af7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39af7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="39af7-112">See Also</span></span>  
 [<span data-ttu-id="39af7-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39af7-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="39af7-114">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="39af7-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
