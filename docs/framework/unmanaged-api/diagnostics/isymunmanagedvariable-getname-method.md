---
title: ISymUnmanagedVariable::GetName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9abbfa14777c5a5f5a77fa91db0fbafee095ba9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429242"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="af45c-102">ISymUnmanagedVariable::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="af45c-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="af45c-103">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="af45c-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af45c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af45c-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af45c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af45c-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="af45c-106">[in] La longitud del búfer que el `pcchName` parámetro señala.</span><span class="sxs-lookup"><span data-stu-id="af45c-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="af45c-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="af45c-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="af45c-108">[out] Búfer que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="af45c-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af45c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af45c-109">Return Value</span></span>  
 <span data-ttu-id="af45c-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="af45c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af45c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af45c-111">Requirements</span></span>  
 <span data-ttu-id="af45c-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="af45c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af45c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="af45c-113">See Also</span></span>  
 [<span data-ttu-id="af45c-114">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af45c-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
