---
description: 'Más información acerca de: ISymUnmanagedWriter:: Closenamespace ((método)'
title: ISymUnmanagedWriter::CloseNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
ms.openlocfilehash: c552d8bc86ab2bbd93918fdd6be3f880b3d83178
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762570"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="c7e74-103">ISymUnmanagedWriter::CloseNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="c7e74-103">ISymUnmanagedWriter::CloseNamespace Method</span></span>

<span data-ttu-id="c7e74-104">Cierra el espacio de nombres abierto más recientemente.</span><span class="sxs-lookup"><span data-stu-id="c7e74-104">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7e74-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7e74-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c7e74-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c7e74-106">Return Value</span></span>  

 <span data-ttu-id="c7e74-107">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c7e74-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7e74-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7e74-108">Requirements</span></span>  

 <span data-ttu-id="c7e74-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c7e74-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e74-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7e74-110">See also</span></span>

- [<span data-ttu-id="c7e74-111">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7e74-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="c7e74-112">Método OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="c7e74-112">OpenNamespace Method</span></span>](isymunmanagedwriter-opennamespace-method.md)
