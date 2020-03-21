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
ms.openlocfilehash: 45268929b6e9ad6ac6423aa0fa2b7b5022bc9179
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176622"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="df8ce-102">ISymUnmanagedScope2::GetConstants (Método)</span><span class="sxs-lookup"><span data-stu-id="df8ce-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="df8ce-103">Obtiene las constantes locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="df8ce-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df8ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df8ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df8ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df8ce-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="df8ce-106">[en] La longitud del búfer `pcConstants` a la que apunta el parámetro.</span><span class="sxs-lookup"><span data-stu-id="df8ce-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="df8ce-107">[fuera] Puntero a `ULONG32` un que recibe el tamaño, en caracteres, del búfer necesario para contener las constantes.</span><span class="sxs-lookup"><span data-stu-id="df8ce-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="df8ce-108">[fuera] El búfer que almacena las constantes.</span><span class="sxs-lookup"><span data-stu-id="df8ce-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df8ce-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df8ce-109">Return Value</span></span>  
 <span data-ttu-id="df8ce-110">S_OK si el método se realiza correctamente; de lo contrario, E_FAIL o algún otro código de error.</span><span class="sxs-lookup"><span data-stu-id="df8ce-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df8ce-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df8ce-111">Requirements</span></span>  
 <span data-ttu-id="df8ce-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df8ce-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df8ce-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df8ce-113">See also</span></span>

- [<span data-ttu-id="df8ce-114">ISymUnmanagedScope2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="df8ce-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
