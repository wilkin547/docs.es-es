---
description: 'Más información acerca de: ISymUnmanagedDispose::D estroy (método)'
title: ISymUnmanagedDispose::Destroy (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
ms.openlocfilehash: 3c13f90e08f2ba0dd7c70acc3321913b14195f1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790209"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="d9a5f-103">ISymUnmanagedDispose::Destroy (Método)</span><span class="sxs-lookup"><span data-stu-id="d9a5f-103">ISymUnmanagedDispose::Destroy Method</span></span>

<span data-ttu-id="d9a5f-104">Hace que el objeto subyacente libere todas las referencias internas y devuelva un error en cualquier llamada posterior al método.</span><span class="sxs-lookup"><span data-stu-id="d9a5f-104">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9a5f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9a5f-105">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d9a5f-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9a5f-106">Return Value</span></span>  

 <span data-ttu-id="d9a5f-107">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d9a5f-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9a5f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9a5f-108">Requirements</span></span>  

 <span data-ttu-id="d9a5f-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d9a5f-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a5f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9a5f-110">See also</span></span>

- [<span data-ttu-id="d9a5f-111">ISymUnmanagedDispose (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9a5f-111">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
