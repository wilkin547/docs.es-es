---
title: "Cambios en tiempo de ejecuci&#243;n en .NET Framework 4.6.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cambios en tiempo de ejecución, .NET Framework"
  - "cambios en tiempo de ejecución, .NET Framework 4.6.1"
  - "compatibilidad de aplicaciones"
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# Cambios en tiempo de ejecuci&#243;n en .NET Framework 4.6.1
En casos poco frecuentes, los cambios en tiempo de ejecución pueden afectar a las aplicaciones existentes que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en una versión posterior del tiempo de ejecución de .NET Framework. También conllevan comportamientos diferentes en las aplicaciones que se ejecutan en distintos entornos en tiempo de ejecución de .NET Framework. El [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] incluye cambios en las áreas siguientes:  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Enlace de WCF con el `TransportWithMessageCredential` modo de seguridad|De forma predeterminada, WCF de enlace que usa el `TransportWithMessageCredential` modo de seguridad no permite los mensajes con unsigned "a" encabezado para las claves de seguridad asimétrico. A partir de las aplicaciones que se ejecutan en el [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], es posible relajado este requisito y recibir mensajes que no han iniciado sesión "" encabezados.|Se trata de un comportamiento opcional. Para permitir que los mensajes con unsigned "a" encabezados, agregue el siguiente valor de configuración para la [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sección del archivo de configuración de la aplicación:<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> Como es una característica opcional, no debería afectar al comportamiento de las aplicaciones existentes.|Borde|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|Cuando un <xref:System.Windows.Controls.ItemsControl> muestra una colección mediante la virtualización (<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) y el desplazamiento de elemento (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>), y cuando se desplaza el control para mostrar un elemento cuyo alto en píxeles difiere de sus vecinos, la <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> recorre en iteración todos los elementos de la colección.   La interfaz de usuario no responde durante esta iteración;  Si la colección es de gran tamaño, esto puede considerarse como un bloqueo.<br /><br /> Se produce esta iteración en otras circunstancias, incluso en las versiones anteriores a la [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Por ejemplo, se produce al desplazarse por píxel (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) al encontrar un elemento con un alto de píxeles diferente y, al desplazarse por el elemento de datos jerárquicos (como en un <xref:System.Windows.Controls.TreeView> control o un <xref:System.Windows.Controls.ItemsControl> con agrupación habilitado) al encontrar un elemento con un número diferente de elementos descendientes a sus vecinos.<br /><br /> En el caso de las alturas de píxeles de desplazamiento de elemento y diferentes, la iteración se introdujo en la [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] para corregir errores en el diseño de los datos jerárquicos.  No es necesaria si los datos sin formato (no tiene ninguna jerarquía) y el [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] no lo hace en ese caso.|Si se produce la iteración en la [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] , pero no en las versiones anteriores, es decir, si la <xref:System.Windows.Controls.ItemsControl> se desplaza elemento una lista plana con elementos de alto de píxeles diferente, existen dos soluciones:<br /><br /> Instalar el [.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md).<br /><br /> Instalar [revisión HR 1605](https://support.microsoft.com/en-us/kb/3154529) para el [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].|Secundaria|  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad de aplicaciones en 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)