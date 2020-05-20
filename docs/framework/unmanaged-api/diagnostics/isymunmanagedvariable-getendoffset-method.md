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
ms.openlocfilehash: 91117eae23d38f3bc608f3203ebe53f92516c9c9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610501"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="4220f-102">ISymUnmanagedVariable::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="4220f-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="4220f-103">Obtiene el desplazamiento final de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="4220f-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="4220f-104">Si se trata de una variable local dentro de un ámbito, el desplazamiento final se encontrará dentro de los desplazamientos definidos para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="4220f-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4220f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4220f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4220f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4220f-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4220f-107">enuncia Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="4220f-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4220f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4220f-108">Return Value</span></span>  
 <span data-ttu-id="4220f-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4220f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4220f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4220f-110">Requirements</span></span>  
 <span data-ttu-id="4220f-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4220f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4220f-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="4220f-112">See also</span></span>

- [<span data-ttu-id="4220f-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4220f-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="4220f-114">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="4220f-114">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)
