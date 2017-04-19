---
title: "Cambios en tiempo de ejecución en .NET Framework 4.6.1 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b8c6ec4d0bad4a769fb4d19a98c9e8a4eda0db78
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-461"></a>Cambios en tiempo de ejecución en .NET Framework 4.6.1
En casos poco frecuentes, los cambios en tiempo de ejecución pueden afectar a las aplicaciones existentes que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en una versión posterior del tiempo de ejecución de .NET Framework. También conllevan comportamientos diferentes en las aplicaciones que se ejecutan en distintos entornos en tiempo de ejecución de .NET Framework. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] incluye cambios en las áreas siguientes:  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Enlace WCF con el modo de seguridad `TransportWithMessageCredential`|De forma predeterminada, el enlace WCF que usa el modo de seguridad `TransportWithMessageCredential` no permite los mensajes con un encabezado "para" sin firmar en las claves de seguridad asimétricas. A partir de las aplicaciones que se ejecutan en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], es posible no ser tan estrictos con este requisito y recibir los mensajes que no tengan encabezados "para" firmados.|Se trata de un comportamiento opcional. Para permitir los mensajes con encabezados "para" sin firmar, agregue la siguiente opción de configuración a la sección [\<<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> Como es una característica opcional, no debería afectar al comportamiento de las aplicaciones existentes.|Borde|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|Cuando <xref:System.Windows.Controls.ItemsControl> muestra una colección mediante virtualización (<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) y desplazamiento de artículos (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>), y cuando el control se desplaza para mostrar un elemento cuya altura en píxeles es distinta a la de los elementos adyacentes, <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> itera en todos los elementos de la colección.   La UI no responde durante esta iteración; si la colección es grande, puede parecer un bloqueo.<br /><br /> La iteración se produce en otras circunstancias, incluso en versiones anteriores a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Por ejemplo, se produce en el desplazamiento de píxeles (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) al encontrar un elemento con una altura en píxeles diferente, en datos jerárquicos de desplazamiento de elementos (como en un control <xref:System.Windows.Controls.TreeView> o <xref:System.Windows.Controls.ItemsControl> con el agrupamiento habilitado) al encontrar un elemento con un número diferente de elementos que los adyacentes.<br /><br /> En el caso del desplazamiento de elementos con alturas en píxeles diferentes, la iteración se introdujo en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] para resolver problemas con la distribución de los datos jerárquicos.  No es necesario con datos planos (sin jerarquía), en cuyo caso, [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] no realiza iteración.|Si la iteración se produce en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], pero no en versiones anteriores (es decir, si <xref:System.Windows.Controls.ItemsControl> realiza desplazamiento de elementos en una lista plana con elementos de diferentes alturas en píxeles), hay dos soluciones:<br /><br /> Instalar [.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md)<br /><br /> Instalar la [revisión HR 1605](https://support.microsoft.com/en-us/kb/3154529) para [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|Secundaria|  
## <a name="see-also"></a>Vea también  
 [Compatibilidad de aplicaciones en 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
