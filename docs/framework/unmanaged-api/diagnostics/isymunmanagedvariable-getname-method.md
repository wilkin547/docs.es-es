---
title: "ISymUnmanagedVariable::GetName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a86a93db6058a8fda42e837388f7fa4cf5c765c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="63ed4-102">ISymUnmanagedVariable::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="63ed4-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="63ed4-103">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="63ed4-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ed4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63ed4-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63ed4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63ed4-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="63ed4-106">[in] La longitud del búfer que el `pcchName` parámetro señala.</span><span class="sxs-lookup"><span data-stu-id="63ed4-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="63ed4-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="63ed4-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="63ed4-108">[out] Búfer que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="63ed4-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63ed4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63ed4-109">Return Value</span></span>  
 <span data-ttu-id="63ed4-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="63ed4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63ed4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63ed4-111">Requirements</span></span>  
 <span data-ttu-id="63ed4-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="63ed4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ed4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="63ed4-113">See Also</span></span>  
 [<span data-ttu-id="63ed4-114">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="63ed4-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
