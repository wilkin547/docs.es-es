---
title: "Opción de codificación de instancias"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a874f88b787a99af0461ff47c3ae246442af2f19
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="instance-encoding-option"></a><span data-ttu-id="483b4-102">Opción de codificación de instancias</span><span class="sxs-lookup"><span data-stu-id="483b4-102">Instance Encoding Option</span></span>
<span data-ttu-id="483b4-103">El **opción de codificación de la instancia** propiedad del almacén de instancia de flujo de trabajo de SQL le permite especificar si el proveedor de persistencia de SQL debe comprimir la información de estado de instancia de flujo de trabajo utilizando el algoritmo GZip antes de guardar el información en la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="483b4-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="483b4-104">Los valores permitidos para esta propiedad son: GZip y Ninguno.</span><span class="sxs-lookup"><span data-stu-id="483b4-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="483b4-105">El valor predeterminado es None.</span><span class="sxs-lookup"><span data-stu-id="483b4-105">The default value is None.</span></span> <span data-ttu-id="483b4-106">En la lista siguiente se describen estas opciones.</span><span class="sxs-lookup"><span data-stu-id="483b4-106">The following list describes these options.</span></span>  
  
1.  <span data-ttu-id="483b4-107">**GZip**.</span><span class="sxs-lookup"><span data-stu-id="483b4-107">**GZip**.</span></span> <span data-ttu-id="483b4-108">El proveedor de persistencia codifica la información de estado mediante el algoritmo del GZip antes de conservar la información de estado en la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="483b4-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2.  <span data-ttu-id="483b4-109">**Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="483b4-109">**None**.</span></span> <span data-ttu-id="483b4-110">El proveedor de persistencia no codifica la información de estado antes de guardar la información en la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="483b4-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="483b4-111">Codificar la información de estado de la instancia de flujo de trabajo mediante GZip reduce el consumo de memoria en SQL Database y también el del consumo de la red si la base de datos reside en un equipo diferente en la red del equipo en el que el host de servicio de flujo de trabajo se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="483b4-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="483b4-112">Un Consejo general es definir la **opción de codificación de la instancia** propiedad **ninguno** si el estado de la instancia de flujo de trabajo es pequeño.</span><span class="sxs-lookup"><span data-stu-id="483b4-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
