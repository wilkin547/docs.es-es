---
title: ISymUnmanagedScope2::GetConstantCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
ms.openlocfilehash: 59f4d85f1d8f24724a2d7eef332ac3b3387b7c91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725864"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="be6a5-102">ISymUnmanagedScope2::GetConstantCount (Método)</span><span class="sxs-lookup"><span data-stu-id="be6a5-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>

<span data-ttu-id="be6a5-103">Obtiene un recuento de las constantes definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="be6a5-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be6a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be6a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be6a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be6a5-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="be6a5-106">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener las constantes.</span><span class="sxs-lookup"><span data-stu-id="be6a5-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be6a5-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="be6a5-107">Return Value</span></span>  

 <span data-ttu-id="be6a5-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="be6a5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be6a5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be6a5-109">Requirements</span></span>  

 <span data-ttu-id="be6a5-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="be6a5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6a5-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be6a5-111">See also</span></span>

- [<span data-ttu-id="be6a5-112">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="be6a5-112">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
