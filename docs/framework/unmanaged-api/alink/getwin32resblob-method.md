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
ms.openlocfilehash: 03f6c97b4a5bbbdc0aeaf7b3f07277e66d7d0e9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684517"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="b08a6-102">GetWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="b08a6-102">GetWin32ResBlob Method</span></span>

<span data-ttu-id="b08a6-103">Recupera el BLOB de recursos de Win32.</span><span class="sxs-lookup"><span data-stu-id="b08a6-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="b08a6-104">Llame a este método después de establecer las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b08a6-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b08a6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b08a6-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b08a6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b08a6-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="b08a6-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b08a6-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b08a6-108">Token de archivo que se usa para recuperar el nombre de archivo que se utilizará al construir el recurso de versión de Win32.</span><span class="sxs-lookup"><span data-stu-id="b08a6-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="b08a6-109">TRUE si file es un archivo DLL, false para un archivo EXE.</span><span class="sxs-lookup"><span data-stu-id="b08a6-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="b08a6-110">Icono opcional que se va a insertar en el BLOB de recursos.</span><span class="sxs-lookup"><span data-stu-id="b08a6-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="b08a6-111">Recibe el BLOB de recursos.</span><span class="sxs-lookup"><span data-stu-id="b08a6-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="b08a6-112">Recibe el tamaño del BLOB.</span><span class="sxs-lookup"><span data-stu-id="b08a6-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b08a6-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b08a6-113">Return Value</span></span>  

 <span data-ttu-id="b08a6-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="b08a6-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b08a6-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b08a6-115">Requirements</span></span>  

 <span data-ttu-id="b08a6-116">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="b08a6-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b08a6-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b08a6-117">See also</span></span>

- [<span data-ttu-id="b08a6-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b08a6-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b08a6-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b08a6-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b08a6-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="b08a6-120">ALink API</span></span>](index.md)
