---
description: 'Más información sobre: método Getscope ('
title: Método GetScope
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
ms.openlocfilehash: cdebda457573e70755b49798ae86eae8f076216b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718367"
---
# <a name="getscope-method"></a><span data-ttu-id="f6432-103">Método GetScope</span><span class="sxs-lookup"><span data-stu-id="f6432-103">GetScope Method</span></span>

<span data-ttu-id="f6432-104">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="f6432-104">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6432-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6432-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6432-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6432-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="f6432-107">IDENTIFICADOR único del ensamblado en el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="f6432-107">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f6432-108">IDENTIFICADOR único del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="f6432-108">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="f6432-109">Ámbito de base cero que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="f6432-109">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="f6432-110">Recibe la interfaz de [interfaz IMetaDataImport](../metadata/imetadataimport-interface.md) para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f6432-110">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6432-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f6432-111">Return Value</span></span>  

 <span data-ttu-id="f6432-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6432-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6432-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6432-113">Requirements</span></span>  

 <span data-ttu-id="f6432-114">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="f6432-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6432-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6432-115">See also</span></span>

- [<span data-ttu-id="f6432-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6432-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f6432-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6432-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f6432-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f6432-118">ALink API</span></span>](index.md)
