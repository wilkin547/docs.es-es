---
title: "Acción de finalización de instancias"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3fa2eb347bc69a89545e6145154306f012e23490
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="instance-completion-action"></a><span data-ttu-id="eb509-102">Acción de finalización de instancias</span><span class="sxs-lookup"><span data-stu-id="eb509-102">Instance Completion Action</span></span>
<span data-ttu-id="eb509-103">El **acción de finalización de la instancia** propiedad del almacén de instancia de flujo de trabajo de SQL le permite especificar si los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias.</span><span class="sxs-lookup"><span data-stu-id="eb509-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="eb509-104">Los valores permitidos para esta propiedad son **DeleteAll** y **DeleteNothing**.</span><span class="sxs-lookup"><span data-stu-id="eb509-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="eb509-105">En la lista siguiente se describen estas opciones:</span><span class="sxs-lookup"><span data-stu-id="eb509-105">The following list describes these options:</span></span>  
  
-   <span data-ttu-id="eb509-106">**DeleteAll (valor predeterminado).**</span><span class="sxs-lookup"><span data-stu-id="eb509-106">**DeleteAll (default).**</span></span> <span data-ttu-id="eb509-107">Si el valor de la propiedad está establecido en DeleteAll, los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias.</span><span class="sxs-lookup"><span data-stu-id="eb509-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>  
  
-   <span data-ttu-id="eb509-108">**DeleteNothing.**</span><span class="sxs-lookup"><span data-stu-id="eb509-108">**DeleteNothing.**</span></span> <span data-ttu-id="eb509-109">Si el valor de la propiedad está establecido en DeleteNothing, los datos y metadatos de instancias de flujo de trabajo se mantienen en la base de datos de persistencia incluso después de que se hayan completado las instancias.</span><span class="sxs-lookup"><span data-stu-id="eb509-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="eb509-110">Mantener la información de estado de la instancia después de que éstas hayan finalizado provoca que el tamaño de la base de datos de persistencia crezca.</span><span class="sxs-lookup"><span data-stu-id="eb509-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="eb509-111">A medida que esto ocurre, tardan más las operaciones de la base de datos que el subsistema de persistencia realiza, de modo que necesita purgar la información de estado de la instancias de la base de datos de persistencia periódicamente para que los servicios se lleven a cabo con el nivel de satisfacción adecuado para sus necesidades de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="eb509-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
