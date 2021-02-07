---
description: 'Más información acerca de: ISymUnmanagedScope:: Getlocalcount ((método)'
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
ms.openlocfilehash: 987d161d273b12810988ef30acb703973098d29c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763447"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="4ebb0-103">ISymUnmanagedScope::GetLocalCount (Método)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-103">ISymUnmanagedScope::GetLocalCount Method</span></span>

<span data-ttu-id="4ebb0-104">Obtiene un recuento de las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-104">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ebb0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ebb0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ebb0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ebb0-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="4ebb0-107">enuncia Un puntero a un `ULONG32` que recibe el recuento de variables locales.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-107">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ebb0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4ebb0-108">Return Value</span></span>  

 <span data-ttu-id="4ebb0-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ebb0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ebb0-110">Requirements</span></span>  

 <span data-ttu-id="4ebb0-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4ebb0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebb0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ebb0-112">See also</span></span>

- [<span data-ttu-id="4ebb0-113">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
