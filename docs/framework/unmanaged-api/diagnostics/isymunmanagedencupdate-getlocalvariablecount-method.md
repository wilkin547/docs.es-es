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
ms.openlocfilehash: 11a75ca89a3537ce8ee72e8ba24401800eacff20
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153782"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="ca963-102">ISymUnmanagedENCUpdate::GetLocalVariableCount (Método)</span><span class="sxs-lookup"><span data-stu-id="ca963-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="ca963-103">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="ca963-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca963-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca963-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca963-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca963-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="ca963-106">[in] El token de metadatos de los métodos.</span><span class="sxs-lookup"><span data-stu-id="ca963-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="ca963-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="ca963-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca963-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ca963-108">Return Value</span></span>  
 <span data-ttu-id="ca963-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ca963-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca963-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca963-110">Requirements</span></span>  
 <span data-ttu-id="ca963-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ca963-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca963-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca963-112">See also</span></span>

- [<span data-ttu-id="ca963-113">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca963-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
