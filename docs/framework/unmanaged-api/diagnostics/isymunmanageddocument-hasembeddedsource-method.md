---
description: 'Más información acerca de: ISymUnmanagedDocument:: Hasembeddedsource ((método)'
title: ISymUnmanagedDocument::HasEmbeddedSource (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: fcab83fea65d9a9e483bff9d2d75714c233718eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710132"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="90dcf-103">ISymUnmanagedDocument::HasEmbeddedSource (Método)</span><span class="sxs-lookup"><span data-stu-id="90dcf-103">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>

<span data-ttu-id="90dcf-104">Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="90dcf-104">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90dcf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90dcf-105">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90dcf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90dcf-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="90dcf-107">enuncia Puntero a una variable que indica si el documento tiene código fuente incrustado en los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="90dcf-107">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90dcf-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="90dcf-108">Return Value</span></span>  

 <span data-ttu-id="90dcf-109">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="90dcf-109">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90dcf-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="90dcf-110">See also</span></span>

- [<span data-ttu-id="90dcf-111">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="90dcf-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
