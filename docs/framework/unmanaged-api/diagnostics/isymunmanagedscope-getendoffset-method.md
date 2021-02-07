---
description: 'Más información acerca de: ISymUnmanagedScope:: Getendoffset ((método)'
title: ISymUnmanagedScope::GetEndOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: ac95b98bb87fbf3dc3b42b5a2e5413f76dfffa34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763482"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="9ded9-103">ISymUnmanagedScope::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="9ded9-103">ISymUnmanagedScope::GetEndOffset Method</span></span>

<span data-ttu-id="9ded9-104">Obtiene el desplazamiento final para este ámbito.</span><span class="sxs-lookup"><span data-stu-id="9ded9-104">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ded9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ded9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ded9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ded9-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="9ded9-107">enuncia Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="9ded9-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ded9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ded9-108">Return Value</span></span>  

 <span data-ttu-id="9ded9-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9ded9-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ded9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ded9-110">Requirements</span></span>  

 <span data-ttu-id="9ded9-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9ded9-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ded9-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ded9-112">See also</span></span>

- [<span data-ttu-id="9ded9-113">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ded9-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="9ded9-114">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="9ded9-114">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
