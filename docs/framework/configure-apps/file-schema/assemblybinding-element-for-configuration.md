---
title: '&lt;assemblyBinding&gt; (elemento) para &lt;configuración&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 12065d8bc484f7bbf77ae18c67df1de0845167b2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083904"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="6a97e-102">\<assemblyBinding > (elemento) para \<configuración ></span><span class="sxs-lookup"><span data-stu-id="6a97e-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="6a97e-103">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="6a97e-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="6a97e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6a97e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6a97e-105">&nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="6a97e-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6a97e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a97e-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="6a97e-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="6a97e-107">Attribute</span></span>

|           | <span data-ttu-id="6a97e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a97e-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6a97e-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="6a97e-109">**xmlns**</span></span> | <span data-ttu-id="6a97e-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="6a97e-110">Required attribute.</span></span><br><br><span data-ttu-id="6a97e-111">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6a97e-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="6a97e-112">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="6a97e-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="6a97e-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="6a97e-113">Parent element</span></span>

|     | <span data-ttu-id="6a97e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a97e-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6a97e-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="6a97e-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="6a97e-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a97e-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="6a97e-117">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="6a97e-117">Child element</span></span>

|     | <span data-ttu-id="6a97e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a97e-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6a97e-119">**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="6a97e-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="6a97e-120">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="6a97e-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6a97e-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a97e-121">Remarks</span></span>

<span data-ttu-id="6a97e-122">El [  **\<linkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) elemento simplifica la administración de ensamblados de componentes al permitir que los archivos de configuración de aplicación para incluir ensamblado en los archivos de configuración ubicaciones conocidas, en lugar de duplicar valores de configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6a97e-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="6a97e-123">El  **\<linkedConfiguration >** elemento no se admite para las aplicaciones con manifiestos en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="6a97e-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="6a97e-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a97e-124">Example</span></span>

<span data-ttu-id="6a97e-125">El ejemplo siguiente muestra cómo incluir un archivo de configuración en el disco duro local:</span><span class="sxs-lookup"><span data-stu-id="6a97e-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="6a97e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a97e-126">See also</span></span>

- [<span data-ttu-id="6a97e-127">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6a97e-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
