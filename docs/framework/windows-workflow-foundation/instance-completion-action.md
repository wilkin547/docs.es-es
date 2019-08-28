---
title: Acción de finalización de instancias
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: 698ac0ed5a7cbd4f6a5623cf8d9b6fbea1128d0a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044339"
---
# <a name="instance-completion-action"></a><span data-ttu-id="f315e-102">Acción de finalización de instancias</span><span class="sxs-lookup"><span data-stu-id="f315e-102">Instance Completion Action</span></span>

<span data-ttu-id="f315e-103">La propiedad acción de finalización de **instancia** del almacén de instancias de flujo de trabajo de SQL le permite especificar si los datos y metadatos de las instancias de flujo de trabajo se eliminan de la base de datos de persistencia una vez completadas las instancias.</span><span class="sxs-lookup"><span data-stu-id="f315e-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="f315e-104">Los valores permitidos para esta propiedad son **DeleteAll** y **DeleteNothing**.</span><span class="sxs-lookup"><span data-stu-id="f315e-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="f315e-105">En la lista siguiente se describen estas opciones:</span><span class="sxs-lookup"><span data-stu-id="f315e-105">The following list describes these options:</span></span>

- <span data-ttu-id="f315e-106">**DeleteAll (valor predeterminado).**</span><span class="sxs-lookup"><span data-stu-id="f315e-106">**DeleteAll (default).**</span></span> <span data-ttu-id="f315e-107">Si el valor de la propiedad está establecido en DeleteAll, los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias.</span><span class="sxs-lookup"><span data-stu-id="f315e-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>

- <span data-ttu-id="f315e-108">**DeleteNothing.**</span><span class="sxs-lookup"><span data-stu-id="f315e-108">**DeleteNothing.**</span></span> <span data-ttu-id="f315e-109">Si el valor de la propiedad está establecido en DeleteNothing, los datos y metadatos de instancias de flujo de trabajo se mantienen en la base de datos de persistencia incluso después de que se hayan completado las instancias.</span><span class="sxs-lookup"><span data-stu-id="f315e-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="f315e-110">Mantener la información de estado de la instancia después de que éstas hayan finalizado provoca que el tamaño de la base de datos de persistencia crezca.</span><span class="sxs-lookup"><span data-stu-id="f315e-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="f315e-111">A medida que esto ocurre, tardan más las operaciones de la base de datos que el subsistema de persistencia realiza, de modo que necesita purgar la información de estado de la instancias de la base de datos de persistencia periódicamente para que los servicios se lleven a cabo con el nivel de satisfacción adecuado para sus necesidades de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f315e-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
