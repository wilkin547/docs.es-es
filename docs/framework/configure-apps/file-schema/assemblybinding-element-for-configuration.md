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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155484"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="d9d47-102">\<elemento de> \<assemblyBinding para la configuración></span><span class="sxs-lookup"><span data-stu-id="d9d47-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="d9d47-103">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="d9d47-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="d9d47-104">configuración &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) \*\* \<assemblyBinding>\*\*</span><span class="sxs-lookup"><span data-stu-id="d9d47-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d9d47-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9d47-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="d9d47-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="d9d47-106">Attribute</span></span>

|           | <span data-ttu-id="d9d47-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9d47-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d9d47-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="d9d47-108">**xmlns**</span></span> | <span data-ttu-id="d9d47-109">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d9d47-109">Required attribute.</span></span><br><br><span data-ttu-id="d9d47-110">Especifica el espacio de nombres XML necesario para el enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d9d47-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="d9d47-111">Utilice la cadena "urn: schemas-microsoft-v1" como valor.</span><span class="sxs-lookup"><span data-stu-id="d9d47-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d9d47-112">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="d9d47-112">Parent element</span></span>

|     | <span data-ttu-id="d9d47-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9d47-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d9d47-114">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="d9d47-114">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="d9d47-115">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d9d47-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="d9d47-116">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="d9d47-116">Child element</span></span>

|     | <span data-ttu-id="d9d47-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9d47-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d9d47-118">**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="d9d47-118">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="d9d47-119">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="d9d47-119">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d9d47-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d9d47-120">Remarks</span></span>

<span data-ttu-id="d9d47-121">El elemento [\*\* \<linkedConfiguration>\*\*](linkedconfiguration-element.md) simplifica la administración de ensamblados de componentes al permitir que los archivos de configuración de la aplicación incluyan archivos de configuración de ensamblados en ubicaciones conocidas, en lugar de duplicar la configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d9d47-121">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="d9d47-122">El \*\* \<elemento linkedConfiguration>\*\* no se admite para aplicaciones con manifiestos en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="d9d47-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="d9d47-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9d47-123">Example</span></span>

<span data-ttu-id="d9d47-124">En el ejemplo siguiente se muestra cómo incluir un archivo de configuración en el disco duro local:</span><span class="sxs-lookup"><span data-stu-id="d9d47-124">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="d9d47-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9d47-125">See also</span></span>

- [<span data-ttu-id="d9d47-126">Esquema de archivo de configuración para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d9d47-126">Configuration file schema for the .NET Framework</span></span>](index.md)
