---
description: 'Más información acerca de: no se puede escribir en el archivo de registro porque si se escribe en él se reduciría el espacio libre en disco por debajo del valor de ReservedSpace'
title: No se puede escribir en el archivo de registro porque reduciría el espacio en disco disponible por debajo del valor ReservedSpace.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ReservedSpaceEncroached
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
ms.openlocfilehash: e02fa9527539169da3ea99f89246dafe82646cff
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456957"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-reduce-free-disk-space-below-reservedspace-value"></a><span data-ttu-id="673b7-103">No se puede escribir en el archivo de registro porque reduciría el espacio en disco disponible por debajo del valor ReservedSpace.</span><span class="sxs-lookup"><span data-stu-id="673b7-103">Unable to write to log file because writing to it would reduce free disk space below ReservedSpace value</span></span>

<span data-ttu-id="673b7-104">La clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> no pudo escribir en el archivo de registro porque:</span><span class="sxs-lookup"><span data-stu-id="673b7-104">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
- <span data-ttu-id="673b7-105">La cantidad de espacio en disco libre (en bytes) es menor que el valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> .</span><span class="sxs-lookup"><span data-stu-id="673b7-105">The amount of free disk space (in bytes) is less than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property</span></span>  
  
     <span data-ttu-id="673b7-106">y</span><span class="sxs-lookup"><span data-stu-id="673b7-106">—and—</span></span>  
  
- <span data-ttu-id="673b7-107">El valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> es <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span><span class="sxs-lookup"><span data-stu-id="673b7-107">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="673b7-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="673b7-108">To correct this error</span></span>  
  
1. <span data-ttu-id="673b7-109">Almacene los registros existentes y quítelos del equipo para permitir que el objeto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> cree nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="673b7-109">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="673b7-110">Cambie el valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> a un número menor para reservar menos espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="673b7-110">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property to a smaller number to reserve less disk space.</span></span>  
  
3. <span data-ttu-id="673b7-111">Establezca la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> en <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> para descartar los mensajes sin advertencia si no hay suficiente espacio en disco libre.</span><span class="sxs-lookup"><span data-stu-id="673b7-111">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if there is not enough free disk space.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673b7-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="673b7-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="673b7-113">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="673b7-113">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="673b7-114">My. Application. info. DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="673b7-114">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
