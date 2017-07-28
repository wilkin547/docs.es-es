---
title: "Mitigación: Referencia cultural y operaciones de distribuidor en aplicaciones WPF"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41fc52679884d547809f1c1e9f47e29eb668cb8e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a>Mitigación: Referencia cultural y operaciones de distribuidor en aplicaciones WPF
En las aplicaciones destinadas a .NET Framework 4.6 y .NET Framework 4.6.1, los cambios de las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> realizados en <xref:System.Windows.Threading.Dispatcher> se pierden al final de dicha operación de distribuidor. De igual modo, los cambios efectuados en <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> fuera de una operación de distribuidor pueden no reflejarse cuando se ejecute dicha operación.  
  
 Esto se debe a que un cambio de <xref:System.Threading.ExecutionContext> da lugar a que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se almacenen en el contexto de ejecución. Las operaciones de distribuidor de WPF almacenan el contexto de ejecución usado para iniciar la operación y restaurar el contexto anterior cuando la operación se complete. Dado que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> ahora forman parte de este contexto, los cambios efectuados en ellas como parte de una operación de distribuidor no persisten fuera de la operación.  
  
## <a name="impact"></a>Impacto  
 En términos prácticos, significa que los cambios efectuados en las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> pueden no transmitirse entre devoluciones de llamadas de la IU de WPF y otro código de alguna aplicación WPF.  
  
## <a name="mitigation"></a>Mitigación  
 Las aplicaciones afectadas por este cambio pueden encontrar una solución alternativa a este problema de dos formas:  
  
-   Al almacenar los objetos <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> deseados y comprobar todos los cuerpos de la operación <xref:System.Windows.Threading.Dispatcher> (incluidos los controladores de devolución de llamadas de eventos de UI) en que los objetos <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> correctos están establecidos.  
  
-   Como el cambio en <xref:System.Threading.ExecutionContext> solo afecta a las aplicaciones WPF destinadas a .NET Framework 4.6 o .NET Framework 4.6.1, podría evitarse con .NET Framework 4.5.2 o a partir de la versión .NET Framework 4.6.2.  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

