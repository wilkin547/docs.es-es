---
title: Esquema de configuración del inicio
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "61701520"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="548dd-102">Esquema de configuración del inicio</span><span class="sxs-lookup"><span data-stu-id="548dd-102">Startup settings schema</span></span>

<span data-ttu-id="548dd-103">La configuración de inicio especifica la versión de Common Language Runtime que debe ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="548dd-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="548dd-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="548dd-104">Element</span></span>|<span data-ttu-id="548dd-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="548dd-105">Description</span></span>|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="548dd-106">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="548dd-106">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="548dd-107">Las aplicaciones compiladas con la versión de tiempo de ejecución 1,1 deben usar el **\<supportedRuntime>** elemento.</span><span class="sxs-lookup"><span data-stu-id="548dd-107">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="548dd-108">Especifica qué versiones de Common Language Runtime admite la aplicación.</span><span class="sxs-lookup"><span data-stu-id="548dd-108">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[\<startup>](startup-element.md)|<span data-ttu-id="548dd-109">Contiene los **\<requiredRuntime>** **\<supportedRuntime>** elementos y.</span><span class="sxs-lookup"><span data-stu-id="548dd-109">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="548dd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="548dd-110">See also</span></span>

- [<span data-ttu-id="548dd-111">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="548dd-111">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="548dd-112">Cómo: Configurar una aplicación para que admita .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="548dd-112">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
