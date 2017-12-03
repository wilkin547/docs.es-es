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
ms.openlocfilehash: 83dec7ef4c911c0bca94caf7cc4c4bf832c8e1b6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="instance-completion-action"></a><span data-ttu-id="d4625-102">Acción de finalización de instancias</span><span class="sxs-lookup"><span data-stu-id="d4625-102">Instance Completion Action</span></span>
<span data-ttu-id="d4625-103">El **acción de finalización de la instancia** propiedad del almacén de instancia de flujo de trabajo de SQL le permite especificar si los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias.</span><span class="sxs-lookup"><span data-stu-id="d4625-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="d4625-104">Los valores permitidos para esta propiedad son **DeleteAll** y **DeleteNothing**.</span><span class="sxs-lookup"><span data-stu-id="d4625-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="d4625-105">En la lista siguiente se describen estas opciones:</span><span class="sxs-lookup"><span data-stu-id="d4625-105">The following list describes these options:</span></span>  
  
-   <span data-ttu-id="d4625-106">**DeleteAll (valor predeterminado).**</span><span class="sxs-lookup"><span data-stu-id="d4625-106">**DeleteAll (default).**</span></span> <span data-ttu-id="d4625-107">Si el valor de la propiedad está establecido en DeleteAll, los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias.</span><span class="sxs-lookup"><span data-stu-id="d4625-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>  
  
-   <span data-ttu-id="d4625-108">**DeleteNothing.**</span><span class="sxs-lookup"><span data-stu-id="d4625-108">**DeleteNothing.**</span></span> <span data-ttu-id="d4625-109">Si el valor de la propiedad está establecido en DeleteNothing, los datos y metadatos de instancias de flujo de trabajo se mantienen en la base de datos de persistencia incluso después de que se hayan completado las instancias.</span><span class="sxs-lookup"><span data-stu-id="d4625-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="d4625-110">Mantener la información de estado de la instancia después de que éstas hayan finalizado provoca que el tamaño de la base de datos de persistencia crezca.</span><span class="sxs-lookup"><span data-stu-id="d4625-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="d4625-111">A medida que esto ocurre, tardan más las operaciones de la base de datos que el subsistema de persistencia realiza, de modo que necesita purgar la información de estado de la instancias de la base de datos de persistencia periódicamente para que los servicios se lleven a cabo con el nivel de satisfacción adecuado para sus necesidades de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d4625-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
