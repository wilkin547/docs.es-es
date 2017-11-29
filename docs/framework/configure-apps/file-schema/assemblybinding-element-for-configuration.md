---
title: "&lt;assemblyBinding&gt; , elemento de &lt;configuración&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2753e290af60d0dcf4efaa79ff3ffffbd7305c27
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="14a67-102">\<assemblyBinding > (elemento) para \<configuración ></span><span class="sxs-lookup"><span data-stu-id="14a67-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="14a67-103">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="14a67-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="14a67-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="14a67-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="14a67-105">&nbsp;&nbsp;**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="14a67-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="14a67-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14a67-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="14a67-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="14a67-107">Attribute</span></span>

|           | <span data-ttu-id="14a67-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="14a67-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="14a67-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="14a67-109">**xmlns**</span></span> | <span data-ttu-id="14a67-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="14a67-110">Required attribute.</span></span><br><br><span data-ttu-id="14a67-111">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="14a67-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="14a67-112">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="14a67-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="14a67-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="14a67-113">Parent element</span></span>

|     | <span data-ttu-id="14a67-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="14a67-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="14a67-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="14a67-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="14a67-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="14a67-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="14a67-117">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="14a67-117">Child element</span></span>

|     | <span data-ttu-id="14a67-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="14a67-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="14a67-119">**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="14a67-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="14a67-120">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="14a67-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="14a67-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14a67-121">Remarks</span></span>

<span data-ttu-id="14a67-122">El [  **\<linkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) elemento simplifica la administración de ensamblados de componentes al permitir que los archivos de configuración de aplicación para incluir los ensamblados de archivos de configuración en ubicaciones bien conocidas, en lugar de duplicar valores de configuración de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="14a67-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="14a67-123">El  **\<linkedConfiguration >** elemento no se admite para las aplicaciones con manifiestos en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="14a67-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="14a67-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14a67-124">Example</span></span>

<span data-ttu-id="14a67-125">En el ejemplo siguiente se muestra cómo incluir un archivo de configuración en el disco duro local:</span><span class="sxs-lookup"><span data-stu-id="14a67-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="14a67-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="14a67-126">See also</span></span>

[<span data-ttu-id="14a67-127">Esquema de archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="14a67-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
