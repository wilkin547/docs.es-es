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
ms.openlocfilehash: 8af71314cf8a24c710d3b8980c082daaf9186715
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501877"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="71d97-102">CorSymSearchPolicyAttributes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="71d97-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="71d97-103">Especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="71d97-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="71d97-104">Estas constantes las usan los métodos [isymunmanagedbinder2 (:: getreaderforfile2 (](isymunmanagedbinder2-getreaderforfile2-method.md) y [Isymunmanagedbinder3 (:: getreaderfromcallback (](isymunmanagedbinder3-getreaderfromcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="71d97-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="71d97-105">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="71d97-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71d97-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71d97-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="71d97-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="71d97-107">Members</span></span>  
  
|<span data-ttu-id="71d97-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="71d97-108">Member</span></span>|<span data-ttu-id="71d97-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="71d97-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="71d97-110">Consulta el registro para buscar rutas de acceso de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="71d97-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="71d97-111">Obtiene acceso a un servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="71d97-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="71d97-112">Busca la ruta de acceso especificada en el directorio de depuración.</span><span class="sxs-lookup"><span data-stu-id="71d97-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="71d97-113">Busca el archivo PDB en el lugar donde está el archivo. exe.</span><span class="sxs-lookup"><span data-stu-id="71d97-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71d97-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71d97-114">Requirements</span></span>  
 <span data-ttu-id="71d97-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="71d97-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d97-116">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="71d97-116">See also</span></span>

- [<span data-ttu-id="71d97-117">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="71d97-117">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
