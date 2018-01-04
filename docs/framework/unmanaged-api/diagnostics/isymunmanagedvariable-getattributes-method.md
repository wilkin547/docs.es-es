---
title: "ISymUnmanagedVariable::GetAttributes (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAttributes
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fa57fcb214f465a57af9638d6f5a44acf746225
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="72c3c-102">ISymUnmanagedVariable::GetAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="72c3c-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="72c3c-103">Obtiene los marcadores de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="72c3c-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72c3c-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72c3c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72c3c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="72c3c-106">[out] Un puntero a un `ULONG32` que recibe los atributos.</span><span class="sxs-lookup"><span data-stu-id="72c3c-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="72c3c-107">El valor devuelto será uno de los valores definidos en el [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="72c3c-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72c3c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="72c3c-108">Return Value</span></span>  
 <span data-ttu-id="72c3c-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="72c3c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72c3c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72c3c-110">Requirements</span></span>  
 <span data-ttu-id="72c3c-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="72c3c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c3c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="72c3c-112">See Also</span></span>  
 [<span data-ttu-id="72c3c-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="72c3c-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
