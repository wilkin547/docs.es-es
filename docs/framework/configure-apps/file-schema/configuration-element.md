---
title: Elemento <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 9a7b25c74763c020c0e19c3f6099db9001acf773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705420"
---
# <a name="configuration-element"></a><span data-ttu-id="6f3aa-102">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="6f3aa-102">\<configuration> element</span></span>

<span data-ttu-id="6f3aa-103">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="6f3aa-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="6f3aa-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6f3aa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f3aa-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="6f3aa-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="6f3aa-106">Attributes</span></span>

<span data-ttu-id="6f3aa-107">Ninguna</span><span class="sxs-lookup"><span data-stu-id="6f3aa-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="6f3aa-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="6f3aa-108">Parent element</span></span>

<span data-ttu-id="6f3aa-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="6f3aa-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="6f3aa-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6f3aa-110">Child elements</span></span>

|     | <span data-ttu-id="6f3aa-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f3aa-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6f3aa-112"> *\*\<assemblyBinding>** </span><span class="sxs-lookup"><span data-stu-id="6f3aa-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="6f3aa-113">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="6f3aa-114"> *\*\<Inicio >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="6f3aa-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="6f3aa-115">Todos los elementos en el esquema de configuración de inicio.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="6f3aa-116"> *\*\<en tiempo de ejecución >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="6f3aa-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="6f3aa-117">Todos los elementos en el esquema de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="6f3aa-118">[ **\<System.Runtime.Remoting >** esquema de configuración](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6f3aa-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="6f3aa-119">Todos los elementos en el esquema de configuración de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="6f3aa-120"> *\*\<system.Net >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="6f3aa-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="6f3aa-121">Todos los elementos en el esquema de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="6f3aa-122"> *\*\<cryptographySettings >** esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="6f3aa-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="6f3aa-123">Todos los elementos en el esquema de configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="6f3aa-124"> *\*\<Configuración >** esquema de secciones</span><span class="sxs-lookup"><span data-stu-id="6f3aa-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="6f3aa-125">Todos los elementos en el esquema de configuración de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="6f3aa-126">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="6f3aa-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="6f3aa-127">Todos los elementos en el esquema de configuración de seguimiento y depuración.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="6f3aa-128">[Esquema de configuración de la configuración de ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6f3aa-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="6f3aa-129">Todos los elementos en el esquema de configuración de ASP.NET, que incluye elementos de configuración de aplicaciones y sitios Web de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="6f3aa-130">Utilizado en *Web.config* archivos.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="6f3aa-131">[ **\<webServices >** esquema de configuración](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6f3aa-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="6f3aa-132">Todos los elementos en el esquema de configuración de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="6f3aa-133">Esquema de configuración web</span><span class="sxs-lookup"><span data-stu-id="6f3aa-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="6f3aa-134">Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="6f3aa-135">Utilizado en *aspnet.config* archivos.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6f3aa-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f3aa-136">Remarks</span></span>

<span data-ttu-id="6f3aa-137">Cada archivo de configuración debe contener exactamente un  **\<configuración >** elemento.</span><span class="sxs-lookup"><span data-stu-id="6f3aa-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f3aa-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f3aa-138">See also</span></span>

- [<span data-ttu-id="6f3aa-139">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f3aa-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
