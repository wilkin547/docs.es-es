---
description: 'Más información acerca de: Windows Forms sección de configuración'
title: Sección de configuración de Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: f1eaf2d74c7645d6cf4580d75e23d8910628cce0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697769"
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
[`<add>`](windows-forms-add-configuration-element.md) | Agrega una clave de valores de configuración con un valor específico. |

### <a name="parent-elements"></a>Elementos primarios

Elemento  |Descripción |
---------|---------|
[\<configuration>](../configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y Windows Forms. |

## <a name="remarks"></a>Observaciones

A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework.

El `<System.Windows.Forms.ApplicationConfigurationSection>` elemento puede incluir uno o varios [`<add>`](windows-forms-add-configuration-element.md) elementos secundarios, cada uno de los cuales define un valor de configuración específico.

## <a name="see-also"></a>Vea también

- [Esquema de los archivos de configuración](../index.md)
- [Compatibilidad con PPP alta en Windows Forms](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)
