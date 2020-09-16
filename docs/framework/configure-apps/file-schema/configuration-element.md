---
title: <configuration> (elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 8f79981a55d0bc9b1cd522e45f5606fda102c72c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544697"
---
# <a name="configuration-element"></a><span data-ttu-id="9beae-102">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="9beae-102">\<configuration> element</span></span>

<span data-ttu-id="9beae-103">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9beae-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="9beae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9beae-104">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="9beae-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="9beae-105">Attributes</span></span>

<span data-ttu-id="9beae-106">None</span><span class="sxs-lookup"><span data-stu-id="9beae-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="9beae-107">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="9beae-107">Parent element</span></span>

<span data-ttu-id="9beae-108">None</span><span class="sxs-lookup"><span data-stu-id="9beae-108">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="9beae-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9beae-109">Child elements</span></span>

|     | <span data-ttu-id="9beae-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9beae-110">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="9beae-111">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="9beae-111">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="9beae-112">**\<startup>** Esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="9beae-112">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="9beae-113">Todos los elementos del esquema de configuración de inicio.</span><span class="sxs-lookup"><span data-stu-id="9beae-113">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="9beae-114">**\<runtime>** Esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="9beae-114">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="9beae-115">Todos los elementos del esquema de configuración de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9beae-115">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="9beae-116">[**\<system.runtime.remoting>** Esquema de configuración](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9beae-116">[**\<system.runtime.remoting>** Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="9beae-117">Todos los elementos del esquema de configuración de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="9beae-117">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="9beae-118">**\<system.Net>** Esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="9beae-118">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="9beae-119">Todos los elementos del esquema de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="9beae-119">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="9beae-120">**\<cryptographySettings>** Esquema de configuración</span><span class="sxs-lookup"><span data-stu-id="9beae-120">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="9beae-121">Todos los elementos del esquema de configuración de cifrado.</span><span class="sxs-lookup"><span data-stu-id="9beae-121">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="9beae-122">**\<configuration>** Esquema de secciones</span><span class="sxs-lookup"><span data-stu-id="9beae-122">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="9beae-123">Todos los elementos del esquema de configuración de la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="9beae-123">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="9beae-124">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="9beae-124">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="9beae-125">Todos los elementos del esquema de configuración de seguimiento y depuración.</span><span class="sxs-lookup"><span data-stu-id="9beae-125">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="9beae-126">[Esquema de opciones de configuración de ASP.NET](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9beae-126">[ASP.NET Configuration Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="9beae-127">Todos los elementos del esquema de configuración ASP.NET, que incluye elementos para configurar sitios web y aplicaciones de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9beae-127">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="9beae-128">Se usa en archivos de *Web.config* .</span><span class="sxs-lookup"><span data-stu-id="9beae-128">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="9beae-129">[**\<webServices>** Esquema de configuración](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9beae-129">[**\<webServices>** Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="9beae-130">Todos los elementos del esquema de configuración de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="9beae-130">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="9beae-131">Esquema de configuración Web</span><span class="sxs-lookup"><span data-stu-id="9beae-131">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="9beae-132">Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.</span><span class="sxs-lookup"><span data-stu-id="9beae-132">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="9beae-133">Se usa en archivos de *aspnet.config* .</span><span class="sxs-lookup"><span data-stu-id="9beae-133">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="9beae-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9beae-134">Remarks</span></span>

<span data-ttu-id="9beae-135">Cada archivo de configuración debe contener exactamente un **\<configuration>** elemento.</span><span class="sxs-lookup"><span data-stu-id="9beae-135">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="9beae-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="9beae-136">See also</span></span>

- [<span data-ttu-id="9beae-137">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9beae-137">Configuration file schema for the .NET Framework</span></span>](index.md)
