---
description: 'Más información acerca de: opción de codificación de instancias'
title: Opción de codificación de instancias
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: 8cca7fd536673ca99b1014173e172508e3d97b7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631169"
---
# <a name="instance-encoding-option"></a><span data-ttu-id="415d9-103">Opción de codificación de instancias</span><span class="sxs-lookup"><span data-stu-id="415d9-103">Instance Encoding Option</span></span>

<span data-ttu-id="415d9-104">La propiedad **opción de codificación de instancias** del almacén de instancias de flujo de trabajo de SQL le permite especificar si el proveedor de persistencia de SQL debe comprimir la información de estado de la instancia de flujo de trabajo mediante el algoritmo gzip antes de guardar la información en la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="415d9-104">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="415d9-105">Los valores permitidos para esta propiedad son: GZip y Ninguno.</span><span class="sxs-lookup"><span data-stu-id="415d9-105">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="415d9-106">El valor predeterminado es Ninguno.</span><span class="sxs-lookup"><span data-stu-id="415d9-106">The default value is None.</span></span> <span data-ttu-id="415d9-107">En la lista siguiente se describen estas opciones.</span><span class="sxs-lookup"><span data-stu-id="415d9-107">The following list describes these options.</span></span>  
  
1. <span data-ttu-id="415d9-108">**Gzip**.</span><span class="sxs-lookup"><span data-stu-id="415d9-108">**GZip**.</span></span> <span data-ttu-id="415d9-109">El proveedor de persistencia codifica la información de estado mediante el algoritmo del GZip antes de conservar la información de estado en la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="415d9-109">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2. <span data-ttu-id="415d9-110">**No**.</span><span class="sxs-lookup"><span data-stu-id="415d9-110">**None**.</span></span> <span data-ttu-id="415d9-111">El proveedor de persistencia no codifica la información de estado antes de guardar la información en la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="415d9-111">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="415d9-112">Codificar la información de estado de la instancia de flujo de trabajo mediante GZip reduce el consumo de memoria en SQL Database y también el del consumo de la red si la base de datos reside en un equipo diferente en la red del equipo en el que el host de servicio de flujo de trabajo se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="415d9-112">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="415d9-113">Una guía general consiste en establecer la propiedad **opción de codificación de instancia** en **ninguno** si el estado de la instancia de flujo de trabajo es pequeño.</span><span class="sxs-lookup"><span data-stu-id="415d9-113">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
