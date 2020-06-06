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
ms.openlocfilehash: 030841330ff37cddb0c9e3e466a55a4be098e784
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088794"
---
# <a name="web-settings-schema"></a><span data-ttu-id="c0d1c-102">Esquema de configuración web</span><span class="sxs-lookup"><span data-stu-id="c0d1c-102">Web Settings Schema</span></span>
<span data-ttu-id="c0d1c-103">La configuración web especifica la configuración de la CPU y de ASP.NET de nivel de ejecución que se aplica al comportamiento de todo el proceso administrado por el nivel de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c0d1c-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="c0d1c-104">Esta configuración difiere de la del tipo de dominio de la aplicación que se especifica en el archivo Web.config de una aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c0d1c-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="c0d1c-105">La configuración web se incluye en los archivos Aspnet.config, que se encuentran en las carpetas de instalación de las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0d1c-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="c0d1c-106">Por ejemplo, el archivo Aspnet. config para .NET Framework 2,0 se encuentra en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="c0d1c-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="c0d1c-107">La configuración web no se usa en otros archivos de configuración, como el archivo machine.config, el archivo raíz Web.config o los archivos Web.config de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0d1c-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)

|<span data-ttu-id="c0d1c-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0d1c-108">Element</span></span>|<span data-ttu-id="c0d1c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0d1c-109">Description</span></span>|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|<span data-ttu-id="c0d1c-110">Contiene información usada por el nivel de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c0d1c-110">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="c0d1c-111">Especifica la configuración de la CPU y de ASP.NET de nivel de ejecución que se aplica al comportamiento de todo el proceso, administrado por el nivel de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c0d1c-111">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0d1c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0d1c-112">See also</span></span>

- [<span data-ttu-id="c0d1c-113">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c0d1c-113">Configuration File Schema</span></span>](../index.md)
