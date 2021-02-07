---
description: 'Más información acerca de: esquema de configuración de inicio'
title: Esquema de configuración del inicio
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: 268b8d8dc2598add61435dd6b07031aa06831737
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726096"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="adf54-103">Esquema de configuración del inicio</span><span class="sxs-lookup"><span data-stu-id="adf54-103">Startup settings schema</span></span>

<span data-ttu-id="adf54-104">La configuración de inicio especifica la versión de Common Language Runtime que debe ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="adf54-104">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="adf54-105">Elemento</span><span class="sxs-lookup"><span data-stu-id="adf54-105">Element</span></span>|<span data-ttu-id="adf54-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="adf54-106">Description</span></span>|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="adf54-107">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="adf54-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="adf54-108">Las aplicaciones compiladas con la versión de tiempo de ejecución 1,1 deben usar el **\<supportedRuntime>** elemento.</span><span class="sxs-lookup"><span data-stu-id="adf54-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="adf54-109">Especifica qué versiones de Common Language Runtime admite la aplicación.</span><span class="sxs-lookup"><span data-stu-id="adf54-109">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[\<startup>](startup-element.md)|<span data-ttu-id="adf54-110">Contiene los **\<requiredRuntime>** **\<supportedRuntime>** elementos y.</span><span class="sxs-lookup"><span data-stu-id="adf54-110">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="adf54-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="adf54-111">See also</span></span>

- [<span data-ttu-id="adf54-112">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="adf54-112">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="adf54-113">Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="adf54-113">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
