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
ms.workload: dotnet
ms.openlocfilehash: f2d83f5dcf6fa93ceba4d670470bd768a2ee1f88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-configuration-section"></a>Sección de configuración de Windows Forms
Las opciones de configuración de Windows Forms permiten a una aplicación de Windows Forms almacenar y recuperar información sobre configuraciones de aplicaciones personalizadas, como la compatibilidad multimonitor, la compatibilidad con valores altos de PPP y otras opciones de configuración predefinidos.

Las opciones de configuración de aplicaciones de Windows Forms se almacenan en un elemento `System.Windows.Forms.ApplicationConfigurationSection` del archivo de configuración de la aplicación.

## <a name="syntax"></a>Sintaxis

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

Ninguno.

### <a name="child-elements"></a>Elementos secundarios

Elemento  |Descripción |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | Agrega una clave de valores de configuración con un valor específico. |

### <a name="parent-elements"></a>Elementos primarios

Elemento  |Descripción |
---------|---------|
[\<configuration>](../configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y Windows Forms. |

## <a name="remarks"></a>Comentarios

A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework. 

El elemento `<System.Windows.Forms.ApplicationConfigurationSection>` puede incluir uno o varios elementos [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) secundarios, y cada uno de ellos define un valor de configuración específico.

## <a name="see-also"></a>Vea también

[Esquema de los archivos de configuración](../index.md)   
[Compatibilidad con valores altos de PPP en Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
