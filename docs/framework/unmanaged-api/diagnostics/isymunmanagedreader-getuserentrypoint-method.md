---
description: 'Más información acerca de: ISymUnmanagedReader:: Getuserentrypoint ((método)'
title: ISymUnmanagedReader::GetUserEntryPoint (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
ms.openlocfilehash: b8696a339fc8aefca2b1a1f9b960ba94ce565d8d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763922"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="ae9bb-103">ISymUnmanagedReader::GetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="ae9bb-103">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>

<span data-ttu-id="ae9bb-104">Devuelve el método que se especificó como punto de entrada del usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="ae9bb-104">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="ae9bb-105">Por ejemplo, este método podría ser el método Main del usuario en lugar de códigos auxiliares generados por el compilador antes del método Main.</span><span class="sxs-lookup"><span data-stu-id="ae9bb-105">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9bb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae9bb-106">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae9bb-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae9bb-107">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="ae9bb-108">enuncia Puntero a una variable que recibe el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="ae9bb-108">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae9bb-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae9bb-109">Return Value</span></span>  

 <span data-ttu-id="ae9bb-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ae9bb-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae9bb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae9bb-111">Requirements</span></span>  

 <span data-ttu-id="ae9bb-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ae9bb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9bb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae9bb-113">See also</span></span>

- [<span data-ttu-id="ae9bb-114">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae9bb-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
