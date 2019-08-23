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
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921246"
---
# <a name="configuration-element"></a><span data-ttu-id="270d2-102">\<elemento Configuration ></span><span class="sxs-lookup"><span data-stu-id="270d2-102">\<configuration> element</span></span>

<span data-ttu-id="270d2-103">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="270d2-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="270d2-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="270d2-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="270d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="270d2-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="270d2-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="270d2-106">Attributes</span></span>

<span data-ttu-id="270d2-107">None</span><span class="sxs-lookup"><span data-stu-id="270d2-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="270d2-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="270d2-108">Parent element</span></span>

<span data-ttu-id="270d2-109">None</span><span class="sxs-lookup"><span data-stu-id="270d2-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="270d2-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="270d2-110">Child elements</span></span>

|     | <span data-ttu-id="270d2-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="270d2-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="270d2-112"> **\<assemblyBinding>** </span><span class="sxs-lookup"><span data-stu-id="270d2-112">**\<assemblyBinding>**</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="270d2-113">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="270d2-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="270d2-114">esquema de configuración de > de inicio  **\<** </span><span class="sxs-lookup"><span data-stu-id="270d2-114">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="270d2-115">Todos los elementos del esquema de configuración de inicio.</span><span class="sxs-lookup"><span data-stu-id="270d2-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="270d2-116">esquema de configuración de **> en tiempo de ejecución \<** </span><span class="sxs-lookup"><span data-stu-id="270d2-116">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="270d2-117">Todos los elementos del esquema de configuración de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="270d2-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="270d2-118">[esquema de configuración de **System. Runtime. Remoting > \<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="270d2-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="270d2-119">Todos los elementos del esquema de configuración de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="270d2-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="270d2-120">esquema de configuración de **> .net del sistema \<** </span><span class="sxs-lookup"><span data-stu-id="270d2-120">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="270d2-121">Todos los elementos del esquema de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="270d2-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="270d2-122">cryptographySettings esquema de configuración de >  **\<** </span><span class="sxs-lookup"><span data-stu-id="270d2-122">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="270d2-123">Todos los elementos del esquema de configuración de cifrado.</span><span class="sxs-lookup"><span data-stu-id="270d2-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="270d2-124">esquema de secciones de Configuration >  **\<** </span><span class="sxs-lookup"><span data-stu-id="270d2-124">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="270d2-125">Todos los elementos del esquema de configuración de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="270d2-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="270d2-126">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="270d2-126">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="270d2-127">Todos los elementos del esquema de configuración de seguimiento y depuración.</span><span class="sxs-lookup"><span data-stu-id="270d2-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="270d2-128">[Esquema de opciones de configuración de ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="270d2-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="270d2-129">Todos los elementos del esquema de configuración ASP.NET, que incluye elementos para configurar sitios web y aplicaciones de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="270d2-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="270d2-130">Se usa en los archivos *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="270d2-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="270d2-131">[esquema de configuración de > de servicios WebService  **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="270d2-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="270d2-132">Todos los elementos del esquema de configuración de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="270d2-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="270d2-133">Esquema de configuración web</span><span class="sxs-lookup"><span data-stu-id="270d2-133">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="270d2-134">Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.</span><span class="sxs-lookup"><span data-stu-id="270d2-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="270d2-135">Se usa en los archivos *Aspnet. config* .</span><span class="sxs-lookup"><span data-stu-id="270d2-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="270d2-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="270d2-136">Remarks</span></span>

<span data-ttu-id="270d2-137">Cada archivo de configuración debe contener exactamente  **\<** un elemento de > de configuración.</span><span class="sxs-lookup"><span data-stu-id="270d2-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="270d2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="270d2-138">See also</span></span>

- [<span data-ttu-id="270d2-139">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="270d2-139">Configuration file schema for the .NET Framework</span></span>](index.md)
