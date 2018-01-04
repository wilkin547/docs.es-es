---
title: ISymUnmanagedWriter4 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5531b491da70cb78de1234e750c2e15390c10ce5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="59c71-102">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="59c71-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="59c71-103">ISymUnmanagedWriter4 (interfaz).</span><span class="sxs-lookup"><span data-stu-id="59c71-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59c71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59c71-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="59c71-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="59c71-105">Methods</span></span>  
 <span data-ttu-id="59c71-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="59c71-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="59c71-107">Método</span><span class="sxs-lookup"><span data-stu-id="59c71-107">Method</span></span>|<span data-ttu-id="59c71-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="59c71-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="59c71-109">GetDebugInfoWithPadding (método)</span><span class="sxs-lookup"><span data-stu-id="59c71-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="59c71-110">Funciona igual que [GetDebugInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) excepto en que la cadena de ruta de acceso se rellena con ceros que siguen el carácter nulo de terminación para que los datos de cadena de un tamaño fijo de `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="59c71-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="59c71-111">Relleno solo se proporciona si la longitud de cadena de ruta de acceso propio es menor que `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="59c71-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="59c71-112">Esto facilita la escritura herramientas que los archivos PE de diferencia.</span><span class="sxs-lookup"><span data-stu-id="59c71-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59c71-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59c71-113">Requirements</span></span>  
 <span data-ttu-id="59c71-114">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="59c71-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59c71-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="59c71-115">See Also</span></span>  
 [<span data-ttu-id="59c71-116">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="59c71-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="59c71-117">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="59c71-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
