---
title: Esquema de configuración web
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: 71b9e46a8c2d60c853af63ee78e2ed5dbe6e98f4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699146"
---
# <a name="web-settings-schema"></a><span data-ttu-id="18f3d-102">Esquema de configuración web</span><span class="sxs-lookup"><span data-stu-id="18f3d-102">Web Settings Schema</span></span>
<span data-ttu-id="18f3d-103">La configuración web especifica la configuración de la CPU y de ASP.NET de nivel de ejecución que se aplica al comportamiento de todo el proceso administrado por el nivel de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="18f3d-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="18f3d-104">Esta configuración difiere de la del tipo de dominio de la aplicación que se especifica en el archivo Web.config de una aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="18f3d-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="18f3d-105">La configuración web se incluye en los archivos Aspnet.config, que se encuentran en las carpetas de instalación de las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18f3d-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="18f3d-106">Por ejemplo, el archivo Aspnet. config para .NET Framework 2,0 se encuentra en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="18f3d-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="18f3d-107">La configuración web no se usa en otros archivos de configuración, como el archivo machine.config, el archivo raíz Web.config o los archivos Web.config de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="18f3d-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
[<span data-ttu-id="18f3d-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="18f3d-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="18f3d-109">&nbsp; @ no__t-1[ **@no__t -4System. Web >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="18f3d-109">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="18f3d-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<applicationPool >** ](applicationpool-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="18f3d-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)</span></span>  
  
|<span data-ttu-id="18f3d-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="18f3d-111">Element</span></span>|<span data-ttu-id="18f3d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="18f3d-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18f3d-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="18f3d-113">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="18f3d-114">Contiene información usada por el nivel de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="18f3d-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="18f3d-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="18f3d-115">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="18f3d-116">Especifica la configuración de la CPU y de ASP.NET de nivel de ejecución que se aplica al comportamiento de todo el proceso, administrado por el nivel de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="18f3d-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18f3d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="18f3d-117">See also</span></span>

- [<span data-ttu-id="18f3d-118">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="18f3d-118">Configuration File Schema</span></span>](../index.md)
