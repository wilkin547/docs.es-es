---
title: "Mitigación: Referencia cultural y operaciones de distribuidor en aplicaciones WPF | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1aee32c5c50c4ff4309f93bff270e6c3b3c8f7cc
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a>Mitigación: Referencia cultural y operaciones de distribuidor en aplicaciones WPF
En las aplicaciones que tienen como destino .NET Framework 4.6 y .NET Framework 4.6.1, los cambios en las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> que se realizan dentro de un <xref:System.Windows.Threading.Dispatcher> se pierden al final de esa operación del distribuidor. De igual forma, es posible que los cambios en <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> realizados fuera de la operación del distribuidor no se reflejen cuando se ejecute la operación.  
  
 Se debe a un cambio en <xref:System.Threading.ExecutionContext> que da lugar a que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se almacenen en el contexto de ejecución. Las operaciones de distribuidor de WPF almacenan el contexto de ejecución usado para iniciar la operación y restaurar el contexto anterior cuando la operación se complete. Como <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> ahora forman parte de dicho contexto, los cambios que experimenten dentro de una operación de distribuidor no persisten fuera de la operación.  
  
## <a name="impact"></a>Impacto  
 Prácticamente, esto significa que los cambios en las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> pueden no fluir entre las devoluciones de llamada de la UI de WPF y otro código en una aplicación WPF.  
  
## <a name="mitigation"></a>Mitigación  
 Las aplicaciones afectadas por este cambio pueden encontrar una solución alternativa a este problema de dos formas:  
  
-   Mediante el almacenamiento de las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> deseadas en un campo y la comprobación en todos los cuerpos de la operación <xref:System.Windows.Threading.Dispatcher> (incluidos los controladores de devolución de llamada de eventos de UI) de que se han establecido las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> correctas.  
  
-   Como el cambio en <xref:System.Threading.ExecutionContext> solo afectan a las aplicaciones WPF destinadas a .NET Framework 4.6 o .NET Framework 4.6.1, podría evitarse con .NET Framework 4.5.2 o a partir de la versión .NET Framework 4.6.2.  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
