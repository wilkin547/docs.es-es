---
title: Elemento <assemblyBinding> para <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155484"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="cfab6-102">Elemento \<assemblyBinding> para \<configuration></span><span class="sxs-lookup"><span data-stu-id="cfab6-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="cfab6-103">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="cfab6-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="cfab6-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="cfab6-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="cfab6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfab6-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="cfab6-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="cfab6-106">Attribute</span></span>

|           | <span data-ttu-id="cfab6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfab6-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="cfab6-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="cfab6-108">**xmlns**</span></span> | <span data-ttu-id="cfab6-109">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="cfab6-109">Required attribute.</span></span><br><br><span data-ttu-id="cfab6-110">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="cfab6-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="cfab6-111">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="cfab6-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="cfab6-112">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="cfab6-112">Parent element</span></span>

|     | <span data-ttu-id="cfab6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfab6-113">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="cfab6-114">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cfab6-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="cfab6-115">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="cfab6-115">Child element</span></span>

|     | <span data-ttu-id="cfab6-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfab6-116">Description</span></span> |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | <span data-ttu-id="cfab6-117">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="cfab6-117">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cfab6-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfab6-118">Remarks</span></span>

<span data-ttu-id="cfab6-119">El [**\<linkedConfiguration>**](linkedconfiguration-element.md) elemento simplifica la administración de ensamblados de componentes al permitir que los archivos de configuración de la aplicación incluyan archivos de configuración de ensamblados en ubicaciones conocidas, en lugar de duplicar las opciones de configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cfab6-119">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="cfab6-120">El **\<linkedConfiguration>** elemento no se admite para las aplicaciones con manifiestos en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="cfab6-120">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="cfab6-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cfab6-121">Example</span></span>

<span data-ttu-id="cfab6-122">En el ejemplo siguiente se muestra cómo incluir un archivo de configuración en el disco duro local:</span><span class="sxs-lookup"><span data-stu-id="cfab6-122">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="cfab6-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfab6-123">See also</span></span>

- [<span data-ttu-id="cfab6-124">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cfab6-124">Configuration file schema for the .NET Framework</span></span>](index.md)
