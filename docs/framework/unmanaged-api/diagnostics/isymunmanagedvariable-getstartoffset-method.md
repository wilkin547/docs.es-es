---
description: 'Más información sobre: ISymUnmanagedVariable:: Getstartoffset ((método)'
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
ms.openlocfilehash: 96ff27cfaf53c7a63c819b1a423e62478cf74832
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762726"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="d9ba5-103">ISymUnmanagedVariable::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="d9ba5-103">ISymUnmanagedVariable::GetStartOffset Method</span></span>

<span data-ttu-id="d9ba5-104">Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="d9ba5-104">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="d9ba5-105">Si se trata de una variable local dentro de un ámbito, el desplazamiento inicial se encontrará dentro de los desplazamientos definidos para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d9ba5-105">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ba5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9ba5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9ba5-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9ba5-107">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="d9ba5-108">enuncia Un puntero a un `ULONG32` que recibe el desplazamiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="d9ba5-108">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9ba5-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9ba5-109">Return Value</span></span>  

 <span data-ttu-id="d9ba5-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d9ba5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9ba5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9ba5-111">Requirements</span></span>  

 <span data-ttu-id="d9ba5-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d9ba5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ba5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9ba5-113">See also</span></span>

- [<span data-ttu-id="d9ba5-114">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9ba5-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="d9ba5-115">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="d9ba5-115">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
