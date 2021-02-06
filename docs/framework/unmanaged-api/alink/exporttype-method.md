---
description: 'Más información sobre: método ExportType'
title: ExportType (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
ms.openlocfilehash: 6dc047cac3b80e6fe7a6f2cd980061b34bb7f286
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638072"
---
# <a name="exporttype-method"></a><span data-ttu-id="193b4-103">ExportType (Método)</span><span class="sxs-lookup"><span data-stu-id="193b4-103">ExportType Method</span></span>

<span data-ttu-id="193b4-104">Especifica que un tipo es exportable.</span><span class="sxs-lookup"><span data-stu-id="193b4-104">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="193b4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="193b4-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="193b4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="193b4-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="193b4-107">IDENTIFICADOR del ensamblado del que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="193b4-107">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="193b4-108">Token de archivo o ID. de ensamblado del archivo que define el tipo exportable.</span><span class="sxs-lookup"><span data-stu-id="193b4-108">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="193b4-109">Token del tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="193b4-109">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="193b4-110">Nombre completo del tipo que se va a convertir en exportable.</span><span class="sxs-lookup"><span data-stu-id="193b4-110">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="193b4-111">`ComType` marcas como `tdPublic` o `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="193b4-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="193b4-112">Este parámetro se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="193b4-112">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="193b4-113">Recibe el token para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="193b4-113">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="193b4-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="193b4-114">Return Value</span></span>  

 <span data-ttu-id="193b4-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="193b4-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="193b4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="193b4-116">Requirements</span></span>  

 <span data-ttu-id="193b4-117">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="193b4-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="193b4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="193b4-118">See also</span></span>

- [<span data-ttu-id="193b4-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="193b4-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="193b4-120">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="193b4-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="193b4-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="193b4-121">ALink API</span></span>](index.md)
