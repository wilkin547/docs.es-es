---
title: ISymUnmanagedVariable::GetStartOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: 68d20c33c5ccd554554cae57ee55f6f51d5d980c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733313"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="c570a-102">ISymUnmanagedVariable::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="c570a-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>

<span data-ttu-id="c570a-103">Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="c570a-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="c570a-104">Si se trata de una variable local dentro de un ámbito, el desplazamiento inicial se encontrará dentro de los desplazamientos definidos para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="c570a-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c570a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c570a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c570a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c570a-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="c570a-107">enuncia Un puntero a un `ULONG32` que recibe el desplazamiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="c570a-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c570a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c570a-108">Return Value</span></span>  

 <span data-ttu-id="c570a-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c570a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c570a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c570a-110">Requirements</span></span>  

 <span data-ttu-id="c570a-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c570a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c570a-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c570a-112">See also</span></span>

- [<span data-ttu-id="c570a-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c570a-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="c570a-114">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="c570a-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
