---
description: 'Más información sobre: ISymUnmanagedScope2:: Getconstantcount ((método)'
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
ms.openlocfilehash: e5b084edb116432aa43360db72ca2528dd3cc6a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763259"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="9de3d-103">ISymUnmanagedScope2::GetConstantCount (Método)</span><span class="sxs-lookup"><span data-stu-id="9de3d-103">ISymUnmanagedScope2::GetConstantCount Method</span></span>

<span data-ttu-id="9de3d-104">Obtiene un recuento de las constantes definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="9de3d-104">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de3d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9de3d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9de3d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9de3d-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="9de3d-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener las constantes.</span><span class="sxs-lookup"><span data-stu-id="9de3d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9de3d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9de3d-108">Return Value</span></span>  

 <span data-ttu-id="9de3d-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9de3d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9de3d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9de3d-110">Requirements</span></span>  

 <span data-ttu-id="9de3d-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9de3d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de3d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9de3d-112">See also</span></span>

- [<span data-ttu-id="9de3d-113">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9de3d-113">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
