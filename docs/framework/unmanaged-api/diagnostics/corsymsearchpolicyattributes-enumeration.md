---
description: 'Más información sobre: enumeración Corsymsearchpolicyattributes ('
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
ms.openlocfilehash: a9af0e96809ec8eba5c03c2e372e818c74914baf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800479"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="0e8e1-103">CorSymSearchPolicyAttributes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0e8e1-103">CorSymSearchPolicyAttributes Enumeration</span></span>

<span data-ttu-id="0e8e1-104">Especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="0e8e1-104">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="0e8e1-105">Estas constantes las usan los métodos [isymunmanagedbinder2 (:: getreaderforfile2 (](isymunmanagedbinder2-getreaderforfile2-method.md) y [Isymunmanagedbinder3 (:: getreaderfromcallback (](isymunmanagedbinder3-getreaderfromcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0e8e1-105">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0e8e1-106">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="0e8e1-106">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e8e1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e8e1-107">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="0e8e1-108">Members</span><span class="sxs-lookup"><span data-stu-id="0e8e1-108">Members</span></span>  
  
|<span data-ttu-id="0e8e1-109">Miembro</span><span class="sxs-lookup"><span data-stu-id="0e8e1-109">Member</span></span>|<span data-ttu-id="0e8e1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e8e1-110">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="0e8e1-111">Consulta el registro para buscar rutas de acceso de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="0e8e1-111">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="0e8e1-112">Obtiene acceso a un servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="0e8e1-112">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="0e8e1-113">Busca la ruta de acceso especificada en el directorio de depuración.</span><span class="sxs-lookup"><span data-stu-id="0e8e1-113">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="0e8e1-114">Busca el archivo PDB en el lugar donde está el archivo. exe.</span><span class="sxs-lookup"><span data-stu-id="0e8e1-114">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e8e1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e8e1-115">Requirements</span></span>  

 <span data-ttu-id="0e8e1-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0e8e1-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8e1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e8e1-117">See also</span></span>

- [<span data-ttu-id="0e8e1-118">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="0e8e1-118">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
