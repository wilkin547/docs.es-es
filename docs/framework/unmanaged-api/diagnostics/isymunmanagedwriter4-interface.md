---
title: ISymUnmanagedWriter4 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: eaf2e8e60d9812ab6a31fb3b9050cbaae0f1a9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609474"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="0d93e-102">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d93e-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="0d93e-103">Interfaz Isymunmanagedwriter4 (.</span><span class="sxs-lookup"><span data-stu-id="0d93e-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d93e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d93e-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="0d93e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0d93e-105">Methods</span></span>  
 <span data-ttu-id="0d93e-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="0d93e-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="0d93e-107">Método</span><span class="sxs-lookup"><span data-stu-id="0d93e-107">Method</span></span>|<span data-ttu-id="0d93e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d93e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d93e-109">Método GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="0d93e-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="0d93e-110">Funciona igual que el [método GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros después del carácter nulo de terminación para convertir los datos de cadena en un tamaño fijo de `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="0d93e-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="0d93e-111">El relleno solo se proporciona si la longitud de la cadena de ruta de acceso es menor que `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="0d93e-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="0d93e-112">Esto facilita la escritura de herramientas que diferencian los archivos PE.</span><span class="sxs-lookup"><span data-stu-id="0d93e-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d93e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d93e-113">Requirements</span></span>  
 <span data-ttu-id="0d93e-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0d93e-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d93e-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0d93e-115">See also</span></span>

- [<span data-ttu-id="0d93e-116">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="0d93e-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="0d93e-117">ISymUnmanagedWriter3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d93e-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
