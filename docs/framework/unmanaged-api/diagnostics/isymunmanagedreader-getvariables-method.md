---
title: ISymUnmanagedReader::GetVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
ms.openlocfilehash: c4341a5ffe557694473ae505590b57d39a27a721
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675898"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="23364-102">ISymUnmanagedReader::GetVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="23364-102">ISymUnmanagedReader::GetVariables Method</span></span>

<span data-ttu-id="23364-103">Devuelve una variable no local, dados su elemento primario y su nombre.</span><span class="sxs-lookup"><span data-stu-id="23364-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23364-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23364-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23364-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23364-105">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="23364-106">de Elemento primario de la variable.</span><span class="sxs-lookup"><span data-stu-id="23364-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="23364-107">[in] Tamaño de la matriz `pVars`.</span><span class="sxs-lookup"><span data-stu-id="23364-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="23364-108">enuncia Puntero a la variable que recibe el número de variables devueltas en `pVars` .</span><span class="sxs-lookup"><span data-stu-id="23364-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="23364-109">enuncia Puntero a la variable que recibe las variables.</span><span class="sxs-lookup"><span data-stu-id="23364-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23364-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="23364-110">Return Value</span></span>  

 <span data-ttu-id="23364-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="23364-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23364-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23364-112">Requirements</span></span>  

 <span data-ttu-id="23364-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="23364-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23364-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23364-114">See also</span></span>

- [<span data-ttu-id="23364-115">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="23364-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
