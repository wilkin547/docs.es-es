---
title: Esquema de configuración de inicio
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701520"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="b7a18-102">Esquema de configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="b7a18-102">Startup settings schema</span></span>

<span data-ttu-id="b7a18-103">La configuración de inicio especifica la versión de Common Language Runtime que debe ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7a18-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="b7a18-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7a18-104">Element</span></span>|<span data-ttu-id="b7a18-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7a18-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7a18-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="b7a18-106">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="b7a18-107">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b7a18-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="b7a18-108">Las aplicaciones compiladas con la versión 1.1 en tiempo de ejecución deberían usar el elemento **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="b7a18-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="b7a18-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="b7a18-109">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="b7a18-110">Especifica qué versiones de Common Language Runtime admite la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7a18-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="b7a18-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="b7a18-111">\<startup></span></span>](startup-element.md)|<span data-ttu-id="b7a18-112">Contiene los elementos **\<requiredRuntime>** y **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="b7a18-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7a18-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7a18-113">See also</span></span>

- [<span data-ttu-id="b7a18-114">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b7a18-114">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b7a18-115">Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="b7a18-115">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
