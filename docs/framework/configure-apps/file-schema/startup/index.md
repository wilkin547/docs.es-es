---
title: Esquema de configuración de inicio
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 0a03438968f487f574606f415fb9d43223030038
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222160"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="58d64-102">Esquema de configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="58d64-102">Startup settings schema</span></span>

<span data-ttu-id="58d64-103">La configuración de inicio especifica la versión de Common Language Runtime que debe ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58d64-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="58d64-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="58d64-104">Element</span></span>|<span data-ttu-id="58d64-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="58d64-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58d64-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="58d64-106">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="58d64-107">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="58d64-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="58d64-108">Las aplicaciones compiladas con la versión 1.1 en tiempo de ejecución deberían usar el elemento **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="58d64-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="58d64-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="58d64-109">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="58d64-110">Especifica qué versiones de Common Language Runtime admite la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58d64-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="58d64-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="58d64-111">\<startup></span></span>](startup-element.md)|<span data-ttu-id="58d64-112">Contiene los elementos **\<requiredRuntime>** y **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="58d64-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58d64-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="58d64-113">See also</span></span>

- [<span data-ttu-id="58d64-114">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="58d64-114">Configuration File Schema</span></span>](../index.md)  
- [<span data-ttu-id="58d64-115">Cómo: Configurar una aplicación para admitir .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="58d64-115">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)