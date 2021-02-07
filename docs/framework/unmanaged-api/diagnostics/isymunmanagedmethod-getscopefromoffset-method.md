---
description: 'Más información sobre: ISymUnmanagedMethod:: GetScopeFromOffset ((método)'
title: ISymUnmanagedMethod::GetScopeFromOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: 87dd1f1732ec5d7c8669dbc2bf73b0b6128aafa1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721325"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="41c92-103">ISymUnmanagedMethod::GetScopeFromOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="41c92-103">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>

<span data-ttu-id="41c92-104">Obtiene el ámbito léxico más envolvente dentro de este método que incluye el desplazamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="41c92-104">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="41c92-105">Se puede usar para iniciar búsquedas de variables locales.</span><span class="sxs-lookup"><span data-stu-id="41c92-105">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41c92-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41c92-106">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41c92-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41c92-107">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="41c92-108">de Un `ULONG` que contiene el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="41c92-108">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="41c92-109">enuncia Puntero que se establece en la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="41c92-109">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41c92-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="41c92-110">Return Value</span></span>  

 <span data-ttu-id="41c92-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="41c92-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41c92-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41c92-112">Requirements</span></span>  

 <span data-ttu-id="41c92-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="41c92-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c92-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="41c92-114">See also</span></span>

- [<span data-ttu-id="41c92-115">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="41c92-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
