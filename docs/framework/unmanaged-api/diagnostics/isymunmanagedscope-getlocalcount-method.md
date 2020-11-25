---
title: ISymUnmanagedScope::GetLocalCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 07c41e9d80b1703e86ae06525d64bf166ef2cf8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717557"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="76026-102">ISymUnmanagedScope::GetLocalCount (Método)</span><span class="sxs-lookup"><span data-stu-id="76026-102">ISymUnmanagedScope::GetLocalCount Method</span></span>

<span data-ttu-id="76026-103">Obtiene un recuento de las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="76026-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76026-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76026-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76026-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76026-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="76026-106">enuncia Un puntero a un `ULONG32` que recibe el recuento de variables locales.</span><span class="sxs-lookup"><span data-stu-id="76026-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76026-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76026-107">Return Value</span></span>  

 <span data-ttu-id="76026-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="76026-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76026-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76026-109">Requirements</span></span>  

 <span data-ttu-id="76026-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="76026-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76026-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76026-111">See also</span></span>

- [<span data-ttu-id="76026-112">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76026-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
