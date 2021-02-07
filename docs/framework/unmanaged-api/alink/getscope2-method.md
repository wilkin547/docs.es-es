---
description: 'Más información sobre: método Getscope2 ('
title: GetScope2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: 9a68f02a638b58e7a70207d8610607bf24b2b96b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718348"
---
# <a name="getscope2-method"></a><span data-ttu-id="2be76-103">GetScope2 (Método)</span><span class="sxs-lookup"><span data-stu-id="2be76-103">GetScope2 Method</span></span>

<span data-ttu-id="2be76-104">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="2be76-104">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be76-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2be76-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="2be76-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2be76-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="2be76-107">IDENTIFICADOR del ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="2be76-107">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2be76-108">IDENTIFICADOR del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="2be76-108">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="2be76-109">Ámbito de base cero que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="2be76-109">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="2be76-110">Recibe un puntero a la interfaz de [interfaz IMetaDataImport2](../metadata/imetadataimport2-interface.md) para el ámbito indicado.</span><span class="sxs-lookup"><span data-stu-id="2be76-110">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2be76-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2be76-111">Return Value</span></span>  

 <span data-ttu-id="2be76-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="2be76-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2be76-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2be76-113">Requirements</span></span>  

 <span data-ttu-id="2be76-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="2be76-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be76-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2be76-115">See also</span></span>

- [<span data-ttu-id="2be76-116">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2be76-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2be76-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2be76-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2be76-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="2be76-118">ALink API</span></span>](index.md)
