---
description: 'Más información sobre: ISymUnmanagedNamespace:: GetVariables ((método)'
title: ISymUnmanagedNamespace::GetVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: 63316bf3ba1e4736d542be3362076c3ae6e95def
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721208"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="b091d-103">ISymUnmanagedNamespace::GetVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="b091d-103">ISymUnmanagedNamespace::GetVariables Method</span></span>

<span data-ttu-id="b091d-104">Devuelve todas las variables definidas en el ámbito global dentro de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b091d-104">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b091d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b091d-105">Syntax</span></span>  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b091d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b091d-106">Parameters</span></span>  

 `cVars`  
 <span data-ttu-id="b091d-107">de `ULONG32` Que indica el tamaño de la `pVars` matriz.</span><span class="sxs-lookup"><span data-stu-id="b091d-107">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="b091d-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b091d-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="b091d-109">enuncia Un puntero a un búfer que contiene los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b091d-109">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b091d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b091d-110">Return Value</span></span>  

 <span data-ttu-id="b091d-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b091d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b091d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b091d-112">Requirements</span></span>  

 <span data-ttu-id="b091d-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b091d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b091d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b091d-114">See also</span></span>

- [<span data-ttu-id="b091d-115">ISymUnmanagedNamespace (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b091d-115">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
