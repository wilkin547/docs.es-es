---
title: Sección de configuración de Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 2d518ec03602580f3c5d00ef2901ff7d7ac1d81b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148508"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="029db-102">Sección de configuración de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="029db-102">Windows Forms Configuration Section</span></span>

<span data-ttu-id="029db-103">Las opciones de configuración de Windows Forms permiten a una aplicación de Windows Forms almacenar y recuperar información sobre configuraciones de aplicaciones personalizadas, como la compatibilidad multimonitor, la compatibilidad con valores altos de PPP y otras opciones de configuración predefinidos.</span><span class="sxs-lookup"><span data-stu-id="029db-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="029db-104">Las opciones de configuración de aplicaciones de Windows Forms se almacenan en un elemento `System.Windows.Forms.ApplicationConfigurationSection` del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="029db-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="029db-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="029db-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="029db-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="029db-106">Attributes and elements</span></span>

<span data-ttu-id="029db-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="029db-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="029db-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="029db-108">Attributes</span></span>

<span data-ttu-id="029db-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="029db-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="029db-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="029db-110">Child elements</span></span>

<span data-ttu-id="029db-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="029db-111">Element</span></span>  |<span data-ttu-id="029db-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="029db-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="029db-113">Agrega una clave de valores de configuración con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="029db-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="029db-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="029db-114">Parent elements</span></span>

<span data-ttu-id="029db-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="029db-115">Element</span></span>  |<span data-ttu-id="029db-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="029db-116">Description</span></span> |
---------|---------|
[\<configuration>](../configuration-element.md) | <span data-ttu-id="029db-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="029db-117">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="029db-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="029db-118">Remarks</span></span>

<span data-ttu-id="029db-119">A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="029db-119">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span>

<span data-ttu-id="029db-120">El `<System.Windows.Forms.ApplicationConfigurationSection>` elemento puede incluir uno o varios [`<add>`](windows-forms-add-configuration-element.md) elementos secundarios, cada uno de los cuales define un valor de configuración específico.</span><span class="sxs-lookup"><span data-stu-id="029db-120">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="029db-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="029db-121">See also</span></span>

- [<span data-ttu-id="029db-122">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="029db-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="029db-123">Compatibilidad con PPP alta en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="029db-123">High DPI Support in Windows Forms</span></span>](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)
