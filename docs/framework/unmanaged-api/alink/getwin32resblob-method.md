---
title: GetWin32ResBlob (Método)
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b26f08548ac964fae2f4d64db50167add327eb2d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777370"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="afb21-102">GetWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="afb21-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="afb21-103">Recupera el BLOB de recursos de Win32.</span><span class="sxs-lookup"><span data-stu-id="afb21-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="afb21-104">Llame a este método después de establecer las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="afb21-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb21-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afb21-105">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="afb21-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="afb21-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="afb21-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="afb21-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="afb21-108">Token de archivo que se usa para recuperar el nombre de archivo que se utilizará al construir el recurso de versión de Win32.</span><span class="sxs-lookup"><span data-stu-id="afb21-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="afb21-109">TRUE si file es un archivo DLL, false para un archivo EXE.</span><span class="sxs-lookup"><span data-stu-id="afb21-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="afb21-110">Icono opcional que se va a insertar en el BLOB de recursos.</span><span class="sxs-lookup"><span data-stu-id="afb21-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="afb21-111">Recibe el BLOB de recursos.</span><span class="sxs-lookup"><span data-stu-id="afb21-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="afb21-112">Recibe el tamaño del BLOB.</span><span class="sxs-lookup"><span data-stu-id="afb21-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afb21-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="afb21-113">Return Value</span></span>  
 <span data-ttu-id="afb21-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="afb21-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afb21-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afb21-115">Requirements</span></span>  
 <span data-ttu-id="afb21-116">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="afb21-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb21-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="afb21-117">See also</span></span>

- [<span data-ttu-id="afb21-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="afb21-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="afb21-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="afb21-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="afb21-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="afb21-120">ALink API</span></span>](index.md)
