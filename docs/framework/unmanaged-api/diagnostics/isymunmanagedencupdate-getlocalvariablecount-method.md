---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7d557e2111a26c0865c20d8eb952c4d42b5604e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436064"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="e964b-102">ISymUnmanagedENCUpdate::GetLocalVariableCount (Método)</span><span class="sxs-lookup"><span data-stu-id="e964b-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="e964b-103">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="e964b-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e964b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e964b-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e964b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e964b-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="e964b-106">[in] El token de metadatos de métodos.</span><span class="sxs-lookup"><span data-stu-id="e964b-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="e964b-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="e964b-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e964b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e964b-108">Return Value</span></span>  
 <span data-ttu-id="e964b-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e964b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e964b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e964b-110">Requirements</span></span>  
 <span data-ttu-id="e964b-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e964b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e964b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e964b-112">See Also</span></span>  
 [<span data-ttu-id="e964b-113">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e964b-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
