---
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
ms.openlocfilehash: 5bd94cb851d4bb044d4ce03b97d6342a2c9652e4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441323"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="dd191-102">ISymUnmanagedDispose::Destroy (Método)</span><span class="sxs-lookup"><span data-stu-id="dd191-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="dd191-103">Hace que el objeto subyacente libere todas las referencias internas y devuelva un error en cualquier llamada posterior al método.</span><span class="sxs-lookup"><span data-stu-id="dd191-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd191-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd191-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dd191-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dd191-105">Return Value</span></span>  
 <span data-ttu-id="dd191-106">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="dd191-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd191-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd191-107">Requirements</span></span>  
 <span data-ttu-id="dd191-108">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="dd191-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd191-109">Consulta también</span><span class="sxs-lookup"><span data-stu-id="dd191-109">See also</span></span>

- [<span data-ttu-id="dd191-110">ISymUnmanagedDispose (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd191-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
