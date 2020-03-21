---
title: Sección de configuración de Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 4de61ae3cb5eb8a3fc226881e2b7f842030dfddf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151837"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="8b830-102">Sección de configuración de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b830-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="8b830-103">Las opciones de configuración de Windows Forms permiten a una aplicación de Windows Forms almacenar y recuperar información sobre configuraciones de aplicaciones personalizadas, como la compatibilidad multimonitor, la compatibilidad con valores altos de PPP y otras opciones de configuración predefinidos.</span><span class="sxs-lookup"><span data-stu-id="8b830-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="8b830-104">Las opciones de configuración de aplicaciones de Windows Forms se almacenan en un elemento `System.Windows.Forms.ApplicationConfigurationSection` del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8b830-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b830-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b830-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8b830-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8b830-106">Attributes and elements</span></span>

<span data-ttu-id="8b830-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8b830-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8b830-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="8b830-108">Attributes</span></span>

<span data-ttu-id="8b830-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8b830-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8b830-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8b830-110">Child elements</span></span>

<span data-ttu-id="8b830-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b830-111">Element</span></span>  |<span data-ttu-id="8b830-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b830-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="8b830-113">Agrega una clave de valores de configuración con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="8b830-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="8b830-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8b830-114">Parent elements</span></span>

<span data-ttu-id="8b830-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b830-115">Element</span></span>  |<span data-ttu-id="8b830-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b830-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="8b830-117">\<configuración></span><span class="sxs-lookup"><span data-stu-id="8b830-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="8b830-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8b830-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="8b830-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8b830-119">Remarks</span></span>

<span data-ttu-id="8b830-120">A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b830-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span>

<span data-ttu-id="8b830-121">El `<System.Windows.Forms.ApplicationConfigurationSection>` elemento puede incluir [`<add>`](windows-forms-add-configuration-element.md) uno o varios elementos secundarios, cada uno de los cuales define una configuración específica.</span><span class="sxs-lookup"><span data-stu-id="8b830-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b830-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b830-122">See also</span></span>

- [<span data-ttu-id="8b830-123">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8b830-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8b830-124">Compatibilidad con PPP altos en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b830-124">High DPI Support in Windows Forms</span></span>](../../../winforms/high-dpi-support-in-windows-forms.md)
