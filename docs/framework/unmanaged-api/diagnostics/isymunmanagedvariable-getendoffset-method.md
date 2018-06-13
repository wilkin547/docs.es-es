---
title: ISymUnmanagedVariable::GetEndOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0f11614c6fa15034ef5fa3d68e41a936a9ff764
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427862"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="41163-102">ISymUnmanagedVariable::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="41163-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="41163-103">Obtiene el desplazamiento final de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="41163-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="41163-104">Si se trata de una variable local dentro de un ámbito, el desplazamiento final se encontrará dentro de los desplazamientos definidos para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="41163-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41163-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41163-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41163-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41163-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="41163-107">[out] Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="41163-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41163-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="41163-108">Return Value</span></span>  
 <span data-ttu-id="41163-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="41163-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41163-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41163-110">Requirements</span></span>  
 <span data-ttu-id="41163-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="41163-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41163-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="41163-112">See Also</span></span>  
 [<span data-ttu-id="41163-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41163-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="41163-114">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="41163-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
