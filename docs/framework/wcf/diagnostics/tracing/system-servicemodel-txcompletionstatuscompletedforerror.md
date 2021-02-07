---
description: 'Más información sobre: System. ServiceModel. TxCompletionStatusCompletedForError'
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 83cd5c258b3a60f69cc94426aed7ccc1d27f6013
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735613"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="5401a-103">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="5401a-103">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>

<span data-ttu-id="5401a-104">La transacción especificada para la operación especificada se completó debido a una excepción de ejecución no controlada.</span><span class="sxs-lookup"><span data-stu-id="5401a-104">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5401a-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="5401a-105">Description</span></span>  

 <span data-ttu-id="5401a-106">Se efectúa el seguimiento cuando se produce un error durante un intento de completar la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="5401a-106">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="5401a-107">Esto sucede antes de que se envíe una respuesta o un error al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5401a-107">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="5401a-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="5401a-108">Troubleshooting</span></span>  

 <span data-ttu-id="5401a-109">Busque en el mensaje de seguimiento el mensaje de excepción y cualquier elemento procesable.</span><span class="sxs-lookup"><span data-stu-id="5401a-109">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5401a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5401a-110">See also</span></span>

- [<span data-ttu-id="5401a-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="5401a-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="5401a-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="5401a-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="5401a-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5401a-113">Administration and Diagnostics</span></span>](../index.md)
