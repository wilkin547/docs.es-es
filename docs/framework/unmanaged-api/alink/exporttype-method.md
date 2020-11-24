---
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
ms.openlocfilehash: b8db08b22765bac0ed2fe058db49d6882b8d22df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684803"
---
# <a name="exporttype-method"></a><span data-ttu-id="f32c6-102">ExportType (Método)</span><span class="sxs-lookup"><span data-stu-id="f32c6-102">ExportType Method</span></span>

<span data-ttu-id="f32c6-103">Especifica que un tipo es exportable.</span><span class="sxs-lookup"><span data-stu-id="f32c6-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f32c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f32c6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f32c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f32c6-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="f32c6-106">IDENTIFICADOR del ensamblado del que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="f32c6-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f32c6-107">Token de archivo o ID. de ensamblado del archivo que define el tipo exportable.</span><span class="sxs-lookup"><span data-stu-id="f32c6-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="f32c6-108">Token del tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="f32c6-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="f32c6-109">Nombre completo del tipo que se va a convertir en exportable.</span><span class="sxs-lookup"><span data-stu-id="f32c6-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f32c6-110">`ComType` marcas como `tdPublic` o `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="f32c6-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="f32c6-111">Este parámetro se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="f32c6-111">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="f32c6-112">Recibe el token para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="f32c6-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f32c6-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f32c6-113">Return Value</span></span>  

 <span data-ttu-id="f32c6-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f32c6-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f32c6-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f32c6-115">Requirements</span></span>  

 <span data-ttu-id="f32c6-116">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="f32c6-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f32c6-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f32c6-117">See also</span></span>

- [<span data-ttu-id="f32c6-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f32c6-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f32c6-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f32c6-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f32c6-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f32c6-120">ALink API</span></span>](index.md)
