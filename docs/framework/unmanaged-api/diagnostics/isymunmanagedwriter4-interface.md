---
title: ISymUnmanagedWriter4 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a5e44541a18f10588e899f59a166406c149691f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650059"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="74ae5-102">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74ae5-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="74ae5-103">ISymUnmanagedWriter4 (interfaz).</span><span class="sxs-lookup"><span data-stu-id="74ae5-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ae5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74ae5-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="74ae5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="74ae5-105">Methods</span></span>  
 <span data-ttu-id="74ae5-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="74ae5-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="74ae5-107">Método</span><span class="sxs-lookup"><span data-stu-id="74ae5-107">Method</span></span>|<span data-ttu-id="74ae5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="74ae5-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74ae5-109">GetDebugInfoWithPadding (método)</span><span class="sxs-lookup"><span data-stu-id="74ae5-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="74ae5-110">Funciona igual que [GetDebugInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros que siguen el carácter nulo de terminación para que los datos de cadena de un tamaño fijo de `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="74ae5-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="74ae5-111">Relleno solo se da si la longitud de cadena de ruta de acceso propio es menor que `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="74ae5-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="74ae5-112">Esto facilita la escritura herramientas que los archivos PE de diferencia.</span><span class="sxs-lookup"><span data-stu-id="74ae5-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74ae5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74ae5-113">Requirements</span></span>  
 <span data-ttu-id="74ae5-114">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="74ae5-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ae5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="74ae5-115">See also</span></span>
- [<span data-ttu-id="74ae5-116">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="74ae5-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="74ae5-117">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74ae5-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
