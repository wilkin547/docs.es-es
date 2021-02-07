---
description: 'Más información acerca de: ISymUnmanagedReader:: GetVariables ((método)'
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
ms.openlocfilehash: 93208e6c5c65c4c770c533b7ea72de513451d97d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763909"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="939d2-103">ISymUnmanagedReader::GetVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="939d2-103">ISymUnmanagedReader::GetVariables Method</span></span>

<span data-ttu-id="939d2-104">Devuelve una variable no local, dados su elemento primario y su nombre.</span><span class="sxs-lookup"><span data-stu-id="939d2-104">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="939d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="939d2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="939d2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="939d2-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="939d2-107">de Elemento primario de la variable.</span><span class="sxs-lookup"><span data-stu-id="939d2-107">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="939d2-108">[in] Tamaño de la matriz `pVars`.</span><span class="sxs-lookup"><span data-stu-id="939d2-108">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="939d2-109">enuncia Puntero a la variable que recibe el número de variables devueltas en `pVars` .</span><span class="sxs-lookup"><span data-stu-id="939d2-109">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="939d2-110">enuncia Puntero a la variable que recibe las variables.</span><span class="sxs-lookup"><span data-stu-id="939d2-110">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="939d2-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="939d2-111">Return Value</span></span>  

 <span data-ttu-id="939d2-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="939d2-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="939d2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="939d2-113">Requirements</span></span>  

 <span data-ttu-id="939d2-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="939d2-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939d2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="939d2-115">See also</span></span>

- [<span data-ttu-id="939d2-116">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="939d2-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
