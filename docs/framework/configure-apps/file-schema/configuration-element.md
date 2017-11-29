---
title: "&lt;configuración&gt; elemento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2241f3e835defe308b94d0cbad96020518dfd19b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-element"></a><span data-ttu-id="93cef-102">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="93cef-102">\<configuration> element</span></span>

<span data-ttu-id="93cef-103">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93cef-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="93cef-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="93cef-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="93cef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93cef-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="93cef-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="93cef-106">Attributes</span></span>

<span data-ttu-id="93cef-107">Ninguna</span><span class="sxs-lookup"><span data-stu-id="93cef-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="93cef-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="93cef-108">Parent element</span></span>

<span data-ttu-id="93cef-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="93cef-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="93cef-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93cef-110">Child elements</span></span>

|     | <span data-ttu-id="93cef-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="93cef-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="93cef-112">**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="93cef-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="93cef-113">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="93cef-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="93cef-114">**\<Inicio >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="93cef-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="93cef-115">Todos los elementos en el esquema de configuración de inicio.</span><span class="sxs-lookup"><span data-stu-id="93cef-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="93cef-116">**\<en tiempo de ejecución >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="93cef-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="93cef-117">Todos los elementos en el esquema de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="93cef-117">All elements in the runtime settings schema.</span></span> |
| [<span data-ttu-id="93cef-118">**\<System.Runtime.Remoting >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="93cef-118">**\<system.runtime.remoting>** Settings Schema</span></span>](http://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | <span data-ttu-id="93cef-119">Todos los elementos en el esquema de configuración de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="93cef-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="93cef-120">**\<system.Net >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="93cef-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="93cef-121">Todos los elementos en el esquema de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="93cef-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="93cef-122">**\<cryptographySettings >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="93cef-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="93cef-123">Todos los elementos en el esquema de configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="93cef-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="93cef-124">**\<Configuración >** esquema de secciones</span><span class="sxs-lookup"><span data-stu-id="93cef-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="93cef-125">Todos los elementos en el esquema de configuración de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="93cef-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="93cef-126">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="93cef-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="93cef-127">Todos los elementos en el esquema de configuración de seguimiento y depuración.</span><span class="sxs-lookup"><span data-stu-id="93cef-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="93cef-128">[Esquema de configuración de configuración de ASP.NET](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="93cef-128">[ASP.NET Configuration Settings Schema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span></span> | <span data-ttu-id="93cef-129">Todos los elementos en el esquema de configuración de ASP.NET, que incluye elementos para configurar aplicaciones y sitios Web de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="93cef-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="93cef-130">Usar en *Web.config* archivos.</span><span class="sxs-lookup"><span data-stu-id="93cef-130">Used in *Web.config* files.</span></span> |
| [<span data-ttu-id="93cef-131">**\<webServices >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="93cef-131">**\<webServices>** Settings Schema</span></span>](http://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | <span data-ttu-id="93cef-132">Todos los elementos en el esquema de configuración de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="93cef-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="93cef-133">Esquema de configuración web</span><span class="sxs-lookup"><span data-stu-id="93cef-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="93cef-134">Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.</span><span class="sxs-lookup"><span data-stu-id="93cef-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="93cef-135">Usar en *aspnet.config* archivos.</span><span class="sxs-lookup"><span data-stu-id="93cef-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="93cef-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93cef-136">Remarks</span></span>

<span data-ttu-id="93cef-137">Cada archivo de configuración debe contener exactamente un  **\<configuración >** elemento.</span><span class="sxs-lookup"><span data-stu-id="93cef-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="93cef-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="93cef-138">See also</span></span>

[<span data-ttu-id="93cef-139">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="93cef-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
