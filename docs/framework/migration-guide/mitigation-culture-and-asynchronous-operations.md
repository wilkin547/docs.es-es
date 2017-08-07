---
title: "Mitigación: Referencia cultural y operaciones asincrónicas"
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
ms.assetid: d2cdb578-9923-47df-9ffd-5865333ac1a4
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: debcae8281c832d2815e1b9896fbbcb725c8ffc3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-asynchronous-operations"></a>Mitigación: Referencia cultural y operaciones asincrónicas
Para las aplicaciones destinadas a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y versiones posteriores, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se almacenan en una clase <xref:System.Threading.ExecutionContext> del subproceso, que fluye a través de operaciones asincrónicas.  
  
## <a name="impact"></a>Impacto  
 A raíz de este cambio, los cambios en <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se reflejan en las tareas ejecutadas posteriormente de forma asincrónica. Esto difiere del comportamiento de las versiones anteriores de .NET Framework, ya que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se restablecerían a los valores predeterminados del sistema en todas las tareas asincrónicas.  
  
## <a name="mitigation"></a>Mitigación  
 Las aplicaciones afectadas por este cambio pueden encontrar una solución alternativa a este problema de dos formas:  
  
-   Establecer de manera explícita la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> deseada como la primera operación en una tarea asincrónica.  
  
-   Optar por el comportamiento anterior de que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> no fluyan, mediante la adición del elemento `AppContextSwitchOverrides` siguiente al archivo de configuración de la aplicación:  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   Optar por el comportamiento anterior de que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> no fluyan, con la configuración mediante programación del siguiente modificador de compatibilidad:  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

