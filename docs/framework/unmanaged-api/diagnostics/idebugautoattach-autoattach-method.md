---
title: IDebugAutoAttach::AutoAttach (Método)
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
ms.openlocfilehash: 64dd653bb0d4e383075a999e0803e4acfd0fae3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720105"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="7b997-102">IDebugAutoAttach::AutoAttach (Método)</span><span class="sxs-lookup"><span data-stu-id="7b997-102">IDebugAutoAttach::AutoAttach Method</span></span>

<span data-ttu-id="7b997-103">Realiza la Asociación automática del depurador invocado por el servidor.</span><span class="sxs-lookup"><span data-stu-id="7b997-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b997-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b997-104">Syntax</span></span>  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b997-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b997-105">Parameters</span></span>  

 `guidPort`  
 <span data-ttu-id="7b997-106">de Siempre se establece en `GUID_NULL` .</span><span class="sxs-lookup"><span data-stu-id="7b997-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="7b997-107">de IDENTIFICADOR de proceso, recuperado normalmente con la `GetCurrentProcessId` función.</span><span class="sxs-lookup"><span data-stu-id="7b997-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="7b997-108">de Tipo de programa: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` o `AUTOATTACH_PROGRAM_UNKNOWN` .</span><span class="sxs-lookup"><span data-stu-id="7b997-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="7b997-109">de IDENTIFICADOR de programa.</span><span class="sxs-lookup"><span data-stu-id="7b997-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="7b997-110">de Cadena pasada por el verbo DEBUG.</span><span class="sxs-lookup"><span data-stu-id="7b997-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b997-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7b997-111">Return Value</span></span>  

 <span data-ttu-id="7b997-112">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="7b997-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b997-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b997-113">Requirements</span></span>  

 <span data-ttu-id="7b997-114">**Encabezado:** DbgAutoAttach. h</span><span class="sxs-lookup"><span data-stu-id="7b997-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b997-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b997-115">See also</span></span>

- [<span data-ttu-id="7b997-116">IDebugAutoAttach (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b997-116">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)
