---
description: 'Más información acerca de: ISymUnmanagedWriter:: Close (método)'
title: ISymUnmanagedWriter::Close (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 02f4d8d4a232240160ad5065947282f40af42f4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762635"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="612e5-103">ISymUnmanagedWriter::Close (Método)</span><span class="sxs-lookup"><span data-stu-id="612e5-103">ISymUnmanagedWriter::Close Method</span></span>

<span data-ttu-id="612e5-104">Cierra el escritor de símbolos después de confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="612e5-104">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="612e5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="612e5-105">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="612e5-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="612e5-106">Return Value</span></span>  

 <span data-ttu-id="612e5-107">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="612e5-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="612e5-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="612e5-108">Remarks</span></span>  

 <span data-ttu-id="612e5-109">Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="612e5-109">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="612e5-110">Para cerrar el escritor de símbolos sin confirmar los símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: ABORT](isymunmanagedwriter-abort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="612e5-110">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="612e5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="612e5-111">Requirements</span></span>  

 <span data-ttu-id="612e5-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="612e5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="612e5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="612e5-113">See also</span></span>

- [<span data-ttu-id="612e5-114">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="612e5-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
