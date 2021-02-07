---
description: 'Más información acerca de: ISymUnmanagedWriter:: CloseMethod ((método)'
title: ISymUnmanagedWriter::CloseMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
ms.openlocfilehash: 8d19de0827f94d52c92852b0d1f2b5567e109c15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762583"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="09674-103">ISymUnmanagedWriter::CloseMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="09674-103">ISymUnmanagedWriter::CloseMethod Method</span></span>

<span data-ttu-id="09674-104">Cierra el método actual.</span><span class="sxs-lookup"><span data-stu-id="09674-104">Closes the current method.</span></span> <span data-ttu-id="09674-105">Una vez que se cierra un método, no se pueden definir más símbolos en él.</span><span class="sxs-lookup"><span data-stu-id="09674-105">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09674-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09674-106">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="09674-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09674-107">Return Value</span></span>  

 <span data-ttu-id="09674-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="09674-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09674-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09674-109">Requirements</span></span>  

 <span data-ttu-id="09674-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="09674-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09674-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="09674-111">See also</span></span>

- [<span data-ttu-id="09674-112">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09674-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="09674-113">Método OpenMethod</span><span class="sxs-lookup"><span data-stu-id="09674-113">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
