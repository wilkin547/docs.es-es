---
title: ISymUnmanagedScope2::GetConstants (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73d4cc609694610aead2a3bfaeed1f5cca5f33fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426422"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="e6368-102">ISymUnmanagedScope2::GetConstants (Método)</span><span class="sxs-lookup"><span data-stu-id="e6368-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="e6368-103">Obtiene las constantes locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="e6368-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6368-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6368-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6368-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6368-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="e6368-106">[in] La longitud del búfer que el `pcConstants` parámetro señala.</span><span class="sxs-lookup"><span data-stu-id="e6368-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="e6368-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener las constantes.</span><span class="sxs-lookup"><span data-stu-id="e6368-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="e6368-108">[out] El búfer que almacena las constantes.</span><span class="sxs-lookup"><span data-stu-id="e6368-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6368-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e6368-109">Return Value</span></span>  
 <span data-ttu-id="e6368-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e6368-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6368-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6368-111">Requirements</span></span>  
 <span data-ttu-id="e6368-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e6368-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6368-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6368-113">See Also</span></span>  
 [<span data-ttu-id="e6368-114">ISymUnmanagedScope2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6368-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
