---
description: 'Más información sobre: IDebugAutoAttach (:: AutoAttach (método)'
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
ms.openlocfilehash: 8abd35b1d94fc074d4dafe424c52c274b1de1541
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800362"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="f1284-103">IDebugAutoAttach::AutoAttach (Método)</span><span class="sxs-lookup"><span data-stu-id="f1284-103">IDebugAutoAttach::AutoAttach Method</span></span>

<span data-ttu-id="f1284-104">Realiza la Asociación automática del depurador invocado por el servidor.</span><span class="sxs-lookup"><span data-stu-id="f1284-104">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1284-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1284-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f1284-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1284-106">Parameters</span></span>  

 `guidPort`  
 <span data-ttu-id="f1284-107">de Siempre se establece en `GUID_NULL` .</span><span class="sxs-lookup"><span data-stu-id="f1284-107">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="f1284-108">de IDENTIFICADOR de proceso, recuperado normalmente con la `GetCurrentProcessId` función.</span><span class="sxs-lookup"><span data-stu-id="f1284-108">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="f1284-109">de Tipo de programa: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` o `AUTOATTACH_PROGRAM_UNKNOWN` .</span><span class="sxs-lookup"><span data-stu-id="f1284-109">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="f1284-110">de IDENTIFICADOR de programa.</span><span class="sxs-lookup"><span data-stu-id="f1284-110">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="f1284-111">de Cadena pasada por el verbo DEBUG.</span><span class="sxs-lookup"><span data-stu-id="f1284-111">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1284-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f1284-112">Return Value</span></span>  

 <span data-ttu-id="f1284-113">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f1284-113">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1284-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1284-114">Requirements</span></span>  

 <span data-ttu-id="f1284-115">**Encabezado:** DbgAutoAttach. h</span><span class="sxs-lookup"><span data-stu-id="f1284-115">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1284-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1284-116">See also</span></span>

- [<span data-ttu-id="f1284-117">IDebugAutoAttach (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1284-117">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)
