---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 2bc71d18480fa19be66cbfa1687a7b63eb548309
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601457"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="ae04d-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="ae04d-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="ae04d-103">La transacción especificada para la operación especificada se completó debido a una excepción de ejecución no controlada.</span><span class="sxs-lookup"><span data-stu-id="ae04d-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ae04d-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae04d-104">Description</span></span>  
 <span data-ttu-id="ae04d-105">Se efectúa el seguimiento cuando se produce un error durante un intento de completar la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="ae04d-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="ae04d-106">Esto sucede antes de que se envíe una respuesta o un error al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ae04d-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ae04d-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="ae04d-107">Troubleshooting</span></span>  
 <span data-ttu-id="ae04d-108">Busque en el mensaje de seguimiento el mensaje de excepción y cualquier elemento procesable.</span><span class="sxs-lookup"><span data-stu-id="ae04d-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae04d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae04d-109">See also</span></span>

- [<span data-ttu-id="ae04d-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="ae04d-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="ae04d-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="ae04d-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ae04d-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ae04d-112">Administration and Diagnostics</span></span>](../index.md)
