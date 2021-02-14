---
description: 'Más información acerca de: no se puede obtener un flujo para el registro'
title: No se pudo obtener un flujo para el registro
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 6eda12eb4dc2b3cf303e543a66e1f2f7d739eb6b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455280"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="eae9f-103">No se pudo obtener un flujo para el registro</span><span class="sxs-lookup"><span data-stu-id="eae9f-103">Unable to obtain a stream for the log</span></span>

<span data-ttu-id="eae9f-104">No se pudo obtener un flujo para el registro.</span><span class="sxs-lookup"><span data-stu-id="eae9f-104">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="eae9f-105">Los nombres de archivo potenciales basados en \<name> ya están en uso.</span><span class="sxs-lookup"><span data-stu-id="eae9f-105">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="eae9f-106">La <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> clase no pudo crear un nuevo archivo de registro porque todos los nombres de archivo de registro posibles basados en \<name> ya están en uso.</span><span class="sxs-lookup"><span data-stu-id="eae9f-106">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="eae9f-107">Si dispone de demasiados archivos de registro, podría ser un indicador de un problema de arquitectura con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eae9f-107">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="eae9f-108">Consulte la documentación sobre la clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> para más información.</span><span class="sxs-lookup"><span data-stu-id="eae9f-108">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eae9f-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="eae9f-109">To correct this error</span></span>  
  
1. <span data-ttu-id="eae9f-110">Establezca la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> en <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> o <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> para incluir una marca de fecha en el nombre del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="eae9f-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2. <span data-ttu-id="eae9f-111">Almacene los registros existentes y quítelos del equipo para permitir que el objeto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> cree nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="eae9f-111">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae9f-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eae9f-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [<span data-ttu-id="eae9f-113">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="eae9f-113">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="eae9f-114">My. Application. info. DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="eae9f-114">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
