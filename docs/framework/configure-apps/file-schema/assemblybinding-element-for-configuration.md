---
title: Elemento <assemblyBinding> para <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: e0b83c4b3573ab6819654e72cac1bf3e4a0ba637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921272"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="2efc0-102">\<assemblyBinding > elemento para \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="2efc0-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="2efc0-103">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="2efc0-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="2efc0-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2efc0-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="2efc0-105">&nbsp;&nbsp; **\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="2efc0-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2efc0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2efc0-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="2efc0-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="2efc0-107">Attribute</span></span>

|           | <span data-ttu-id="2efc0-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2efc0-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="2efc0-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="2efc0-109">**xmlns**</span></span> | <span data-ttu-id="2efc0-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="2efc0-110">Required attribute.</span></span><br><br><span data-ttu-id="2efc0-111">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2efc0-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="2efc0-112">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="2efc0-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="2efc0-113">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="2efc0-113">Parent element</span></span>

|     | <span data-ttu-id="2efc0-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2efc0-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2efc0-115"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2efc0-115">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="2efc0-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2efc0-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="2efc0-117">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="2efc0-117">Child element</span></span>

|     | <span data-ttu-id="2efc0-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2efc0-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2efc0-119"> **\<linkedConfiguration>** </span><span class="sxs-lookup"><span data-stu-id="2efc0-119">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="2efc0-120">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="2efc0-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2efc0-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2efc0-121">Remarks</span></span>

<span data-ttu-id="2efc0-122">El elemento > linkedConfiguration simplifica la administración de ensamblados de componentes al permitir que los archivos de configuración de la aplicación incluyan archivos de configuración de ensamblados en ubicaciones conocidas, en lugar de duplicar el ensamblado. [ **\<** ](linkedconfiguration-element.md) Opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="2efc0-122">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="2efc0-123">El elemento > linkedConfiguration no se admite para las aplicaciones con manifiestos en paralelo de Windows.  **\<**</span><span class="sxs-lookup"><span data-stu-id="2efc0-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="2efc0-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2efc0-124">Example</span></span>

<span data-ttu-id="2efc0-125">En el ejemplo siguiente se muestra cómo incluir un archivo de configuración en el disco duro local:</span><span class="sxs-lookup"><span data-stu-id="2efc0-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2efc0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2efc0-126">See also</span></span>

- [<span data-ttu-id="2efc0-127">Esquema del archivo de configuración para el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2efc0-127">Configuration file schema for the .NET Framework</span></span>](index.md)
