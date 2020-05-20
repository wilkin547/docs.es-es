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
ms.openlocfilehash: f2996349fd2bf1765a3de5b67d3296a25b1eaa5e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610371"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="0f077-102">ISymUnmanagedVariable::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="0f077-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="0f077-103">Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="0f077-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="0f077-104">Si se trata de una variable local dentro de un ámbito, el desplazamiento inicial se encontrará dentro de los desplazamientos definidos para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="0f077-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f077-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f077-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f077-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f077-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0f077-107">enuncia Un puntero a un `ULONG32` que recibe el desplazamiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="0f077-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f077-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0f077-108">Return Value</span></span>  
 <span data-ttu-id="0f077-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0f077-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f077-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f077-110">Requirements</span></span>  
 <span data-ttu-id="0f077-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0f077-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f077-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0f077-112">See also</span></span>

- [<span data-ttu-id="0f077-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f077-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="0f077-114">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="0f077-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
