---
title: Esquema de la configuración de inicio
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 4cdf6a051552ab1effd9c4d9c783297a62602f7a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078167"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="9b2d5-102">Esquema de la configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="9b2d5-102">Startup Settings Schema</span></span>
<span data-ttu-id="9b2d5-103">La configuración de inicio especifica la versión de Common Language Runtime que debe ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9b2d5-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="9b2d5-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b2d5-104">Element</span></span>|<span data-ttu-id="9b2d5-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b2d5-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b2d5-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="9b2d5-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="9b2d5-107">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9b2d5-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="9b2d5-108">Las aplicaciones compiladas con la versión 1.1 en tiempo de ejecución deberían usar el elemento **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="9b2d5-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="9b2d5-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="9b2d5-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="9b2d5-110">Especifica qué versiones de Common Language Runtime admite la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9b2d5-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="9b2d5-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="9b2d5-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="9b2d5-112">Contiene los elementos **\<requiredRuntime>** y **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="9b2d5-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b2d5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b2d5-113">See Also</span></span>  
 [<span data-ttu-id="9b2d5-114">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9b2d5-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="9b2d5-115">\<PaveOver> Especificar la versión en tiempo de ejecución que se va a usar</span><span class="sxs-lookup"><span data-stu-id="9b2d5-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
