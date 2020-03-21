---
title: CorSymSearchPolicyAttributes (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 786e53d43ecde0bc3a97fadb77184d25d41430bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178345"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="06ade-102">CorSymSearchPolicyAttributes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="06ade-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="06ade-103">Especifica la directiva que se utilizará al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="06ade-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="06ade-104">Estas constantes las usan los métodos [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3::GetReaderFromCallback.](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)</span><span class="sxs-lookup"><span data-stu-id="06ade-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="06ade-105">Es un riesgo para la seguridad abrir un archivo de base de datos de programas (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="06ade-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ade-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06ade-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="06ade-107">Members</span><span class="sxs-lookup"><span data-stu-id="06ade-107">Members</span></span>  
  
|<span data-ttu-id="06ade-108">Member</span><span class="sxs-lookup"><span data-stu-id="06ade-108">Member</span></span>|<span data-ttu-id="06ade-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="06ade-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="06ade-110">Consulta al registro las rutas de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="06ade-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="06ade-111">Accede a un servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="06ade-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="06ade-112">Busca la ruta de acceso especificada en el directorio Debug.</span><span class="sxs-lookup"><span data-stu-id="06ade-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="06ade-113">Busca el PDB en el lugar donde se encuentra el archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="06ade-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06ade-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06ade-114">Requirements</span></span>  
 <span data-ttu-id="06ade-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="06ade-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ade-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06ade-116">See also</span></span>

- [<span data-ttu-id="06ade-117">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="06ade-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
