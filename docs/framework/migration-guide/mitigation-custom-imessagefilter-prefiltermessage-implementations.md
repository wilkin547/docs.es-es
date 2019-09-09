---
title: 'Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage'
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2af81468c5c4c4caf2f09725d6c7c4723084e35c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779434"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage

En las aplicaciones de Windows Forms destinadas a versiones de .NET Framework a partir de .NET Framework 4.6.1, una implementación personalizada de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> puede filtrar mensajes de forma segura al llamar al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> si la implementación de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>:

- Realiza una o dos de las siguientes acciones:

  - Agregar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.

  - Quitar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. .

- El elemento **And** proporciona mensajes mediante una llamada al método <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>.

## <a name="impact"></a>Impacto

Este cambio solo afecta a aplicaciones de Windows Forms que tienen como destino versiones de .NET Framework a partir de .NET Framework 4.6.1.

Para las aplicaciones de Windows Forms destinadas a las versiones anteriores de .NET Framework, en algunos casos, tales implementaciones inician una excepción <xref:System.IndexOutOfRangeException> cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>.

## <a name="mitigation"></a>Mitigación

Si no quiere este cambio, las aplicaciones que tienen como destino .NET Framework 4.6.1 o una versión posterior pueden optar por no recibirlo agregando el siguiente ajuste de configuración a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.6.1 o una versión posterior, pueden optar por recibir en este comportamiento agregando el siguiente ajuste de configuración a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a>Vea también

- [Cambios de redestinación](retargeting-changes-in-the-net-framework-4-6-1.md)
