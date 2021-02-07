---
description: 'Más información sobre: <assemblyBinding> elemento para <configuration>'
title: Elemento <assemblyBinding> para <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 5cc3fc7cccd4b9dc7b62815734ff76e32e2243d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730114"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="f6194-103">Elemento \<assemblyBinding> para \<configuration></span><span class="sxs-lookup"><span data-stu-id="f6194-103">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="f6194-104">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="f6194-104">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="f6194-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="f6194-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f6194-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6194-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="f6194-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="f6194-107">Attribute</span></span>

|           | <span data-ttu-id="f6194-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6194-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f6194-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="f6194-109">**xmlns**</span></span> | <span data-ttu-id="f6194-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="f6194-110">Required attribute.</span></span><br><br><span data-ttu-id="f6194-111">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f6194-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="f6194-112">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="f6194-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f6194-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="f6194-113">Parent element</span></span>

|     | <span data-ttu-id="f6194-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6194-114">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="f6194-115">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6194-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="f6194-116">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="f6194-116">Child element</span></span>

|     | <span data-ttu-id="f6194-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6194-117">Description</span></span> |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | <span data-ttu-id="f6194-118">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="f6194-118">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f6194-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f6194-119">Remarks</span></span>

<span data-ttu-id="f6194-120">El [**\<linkedConfiguration>**](linkedconfiguration-element.md) elemento simplifica la administración de ensamblados de componentes al permitir que los archivos de configuración de la aplicación incluyan archivos de configuración de ensamblados en ubicaciones conocidas, en lugar de duplicar las opciones de configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f6194-120">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="f6194-121">El **\<linkedConfiguration>** elemento no se admite para las aplicaciones con manifiestos en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="f6194-121">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="f6194-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6194-122">Example</span></span>

<span data-ttu-id="f6194-123">En el ejemplo siguiente se muestra cómo incluir un archivo de configuración en el disco duro local:</span><span class="sxs-lookup"><span data-stu-id="f6194-123">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f6194-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6194-124">See also</span></span>

- [<span data-ttu-id="f6194-125">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f6194-125">Configuration file schema for the .NET Framework</span></span>](index.md)
