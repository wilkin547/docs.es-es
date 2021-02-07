---
description: 'Más información acerca de: <configuration> elemento'
title: <configuration> (elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: ee48a45ddb987201e84213a0d7674da004951ab1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699003"
---
# <a name="configuration-element"></a><span data-ttu-id="a51ac-103">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="a51ac-103">\<configuration> element</span></span>

<span data-ttu-id="a51ac-104">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a51ac-104">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="a51ac-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a51ac-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="a51ac-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a51ac-106">Attributes</span></span>

<span data-ttu-id="a51ac-107">None</span><span class="sxs-lookup"><span data-stu-id="a51ac-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="a51ac-108">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="a51ac-108">Parent element</span></span>

<span data-ttu-id="a51ac-109">None</span><span class="sxs-lookup"><span data-stu-id="a51ac-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="a51ac-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a51ac-110">Child elements</span></span>

|     | <span data-ttu-id="a51ac-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a51ac-111">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="a51ac-112">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="a51ac-112">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="a51ac-113">**\<startup>** Esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="a51ac-113">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="a51ac-114">Todos los elementos del esquema de configuración de inicio.</span><span class="sxs-lookup"><span data-stu-id="a51ac-114">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="a51ac-115">**\<runtime>** Esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="a51ac-115">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="a51ac-116">Todos los elementos del esquema de configuración de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a51ac-116">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="a51ac-117">[**\<system.runtime.remoting>** Esquema de configuración](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a51ac-117">[**\<system.runtime.remoting>** Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="a51ac-118">Todos los elementos del esquema de configuración de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="a51ac-118">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="a51ac-119">**\<system.Net>** Esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="a51ac-119">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="a51ac-120">Todos los elementos del esquema de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="a51ac-120">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="a51ac-121">**\<cryptographySettings>** Esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="a51ac-121">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="a51ac-122">Todos los elementos del esquema de configuración de cifrado.</span><span class="sxs-lookup"><span data-stu-id="a51ac-122">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="a51ac-123">**\<configuration>** Esquema de secciones</span><span class="sxs-lookup"><span data-stu-id="a51ac-123">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="a51ac-124">Todos los elementos del esquema de configuración de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="a51ac-124">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="a51ac-125">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="a51ac-125">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="a51ac-126">Todos los elementos del esquema de configuración de seguimiento y depuración.</span><span class="sxs-lookup"><span data-stu-id="a51ac-126">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="a51ac-127">[Esquema de opciones de configuración de ASP.NET](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a51ac-127">[ASP.NET Configuration Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="a51ac-128">Todos los elementos del esquema de configuración ASP.NET, que incluye elementos para configurar sitios web y aplicaciones de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a51ac-128">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="a51ac-129">Se usa en archivos de *Web.config* .</span><span class="sxs-lookup"><span data-stu-id="a51ac-129">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="a51ac-130">[**\<webServices>** Esquema de configuración](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a51ac-130">[**\<webServices>** Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="a51ac-131">Todos los elementos del esquema de configuración de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="a51ac-131">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="a51ac-132">Esquema de configuración Web</span><span class="sxs-lookup"><span data-stu-id="a51ac-132">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="a51ac-133">Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.</span><span class="sxs-lookup"><span data-stu-id="a51ac-133">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="a51ac-134">Se usa en archivos de *aspnet.config* .</span><span class="sxs-lookup"><span data-stu-id="a51ac-134">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a51ac-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a51ac-135">Remarks</span></span>

<span data-ttu-id="a51ac-136">Cada archivo de configuración debe contener exactamente un **\<configuration>** elemento.</span><span class="sxs-lookup"><span data-stu-id="a51ac-136">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="a51ac-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="a51ac-137">See also</span></span>

- [<span data-ttu-id="a51ac-138">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a51ac-138">Configuration file schema for the .NET Framework</span></span>](index.md)
