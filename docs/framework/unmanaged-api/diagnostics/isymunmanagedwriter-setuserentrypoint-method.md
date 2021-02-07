---
description: 'Más información acerca de: ISymUnmanagedWriter:: Setuserentrypoint ((método)'
title: ISymUnmanagedWriter::SetUserEntryPoint (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
ms.openlocfilehash: a01d23a0462fabd7a2fc259722dcdf2a1c8e0a4c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761985"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="1e287-103">ISymUnmanagedWriter::SetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="1e287-103">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>

<span data-ttu-id="1e287-104">Especifica el método definido por el usuario que es el punto de entrada de este módulo.</span><span class="sxs-lookup"><span data-stu-id="1e287-104">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="1e287-105">Por ejemplo, este punto de entrada podría ser el método Main del usuario en lugar de los códigos auxiliares generados por el compilador antes de Main.</span><span class="sxs-lookup"><span data-stu-id="1e287-105">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e287-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e287-106">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e287-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e287-107">Parameters</span></span>  

 `entryMethod`  
 <span data-ttu-id="1e287-108">de Símbolo (token) de metadatos para el método que es el punto de entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="1e287-108">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e287-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1e287-109">Return Value</span></span>  

 <span data-ttu-id="1e287-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1e287-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e287-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e287-111">Requirements</span></span>  

 <span data-ttu-id="1e287-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1e287-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e287-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e287-113">See also</span></span>

- [<span data-ttu-id="1e287-114">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e287-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
