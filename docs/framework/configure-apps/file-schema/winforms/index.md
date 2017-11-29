---
title: "Sección de configuración de Windows Forms"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b83f00f82de727812c5737915a6dc35ec98e4734
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="d28eb-102">Sección de configuración de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d28eb-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="d28eb-103">Las opciones de configuración de Windows Forms permiten a una aplicación de Windows Forms almacenar y recuperar información sobre configuraciones de aplicaciones personalizadas, como la compatibilidad multimonitor, la compatibilidad con valores altos de PPP y otras opciones de configuración predefinidos.</span><span class="sxs-lookup"><span data-stu-id="d28eb-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="d28eb-104">Las opciones de configuración de aplicaciones de Windows Forms se almacenan en un elemento `System.Windows.Forms.ApplicationConfigurationSection` del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d28eb-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="d28eb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d28eb-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d28eb-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d28eb-106">Attributes and elements</span></span>

<span data-ttu-id="d28eb-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d28eb-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d28eb-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d28eb-108">Attributes</span></span>

<span data-ttu-id="d28eb-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d28eb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d28eb-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d28eb-110">Child elements</span></span>

<span data-ttu-id="d28eb-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="d28eb-111">Element</span></span>  |<span data-ttu-id="d28eb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d28eb-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="d28eb-113">Agrega una clave de valores de configuración con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="d28eb-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="d28eb-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d28eb-114">Parent elements</span></span>

<span data-ttu-id="d28eb-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d28eb-115">Element</span></span>  |<span data-ttu-id="d28eb-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d28eb-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="d28eb-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d28eb-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="d28eb-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d28eb-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="d28eb-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d28eb-119">Remarks</span></span>

<span data-ttu-id="d28eb-120">A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d28eb-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="d28eb-121">El elemento `<System.Windows.Forms.ApplicationConfigurationSection>` puede incluir uno o varios elementos [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) secundarios, y cada uno de ellos define un valor de configuración específico.</span><span class="sxs-lookup"><span data-stu-id="d28eb-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="d28eb-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d28eb-122">See also</span></span>

<span data-ttu-id="d28eb-123">[Esquema de los archivos de configuración](../index.md) </span><span class="sxs-lookup"><span data-stu-id="d28eb-123">[Configuration File Schema](../index.md) </span></span>  
[<span data-ttu-id="d28eb-124">Compatibilidad con valores altos de PPP en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d28eb-124">High DPI Support in Windows Forms</span></span>](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
