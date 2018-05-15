---
title: Campo de Connection.m_WriteList
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d145f6fd21989ada49a581ebf2694dcd56d94351
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="71bba-102">Connection.m\_WriteList campo</span><span class="sxs-lookup"><span data-stu-id="71bba-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="71bba-103">`Connection.m_WriteList` es un <xref:System.Collections.ArrayList> de <xref:System.Net.HttpWebRequest> objetos que se ponen en cola para ser enviados a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="71bba-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="71bba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71bba-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="71bba-105">El `Connection.m_WriteList` campo es privado y no están hechos para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="71bba-105">The `Connection.m_WriteList` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="71bba-106">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="71bba-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="71bba-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71bba-107">Requirements</span></span>

<span data-ttu-id="71bba-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="71bba-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="71bba-109">**Ensamblado:** sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="71bba-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="71bba-110">**Versiones de .NET framework:** disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="71bba-110">**.NET Framework versions:** Available since 2.0.</span></span>
