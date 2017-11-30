---
title: "ISymUnmanagedENCUpdate::GetLocalVariableCount (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3f0a47012a2e6e1f6fec1a363c3b514e45bee396
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="42917-102">ISymUnmanagedENCUpdate::GetLocalVariableCount (Método)</span><span class="sxs-lookup"><span data-stu-id="42917-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="42917-103">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="42917-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42917-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42917-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42917-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42917-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="42917-106">[in] El token de metadatos de métodos.</span><span class="sxs-lookup"><span data-stu-id="42917-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="42917-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="42917-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42917-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42917-108">Return Value</span></span>  
 <span data-ttu-id="42917-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="42917-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42917-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42917-110">Requirements</span></span>  
 <span data-ttu-id="42917-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="42917-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42917-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="42917-112">See Also</span></span>  
 [<span data-ttu-id="42917-113">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42917-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
