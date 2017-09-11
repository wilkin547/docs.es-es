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
# <a name="mitigation-culture-and-asynchronous-operations"></a><span data-ttu-id="bcd9a-102">Mitigación: Referencia cultural y operaciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="bcd9a-102">Mitigation: Culture and Asynchronous Operations</span></span>
<span data-ttu-id="bcd9a-103">Para las aplicaciones destinadas a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y versiones posteriores, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se almacenan en una clase <xref:System.Threading.ExecutionContext> del subproceso, que fluye a través de operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-103">For apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later versions, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are stored in a thread's <xref:System.Threading.ExecutionContext>, which flows across asynchronous operations.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="bcd9a-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="bcd9a-104">Impact</span></span>  
 <span data-ttu-id="bcd9a-105">A raíz de este cambio, los cambios en <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se reflejan en las tareas ejecutadas posteriormente de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-105">As a result of this change, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are reflected in tasks which are later run asynchronously.</span></span> <span data-ttu-id="bcd9a-106">Esto difiere del comportamiento de las versiones anteriores de .NET Framework, ya que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se restablecerían a los valores predeterminados del sistema en todas las tareas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-106">This differs from the behavior of previous .NET Framework versions, which would reset <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to the system default  in all asynchronous tasks.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="bcd9a-107">Mitigación</span><span class="sxs-lookup"><span data-stu-id="bcd9a-107">Mitigation</span></span>  
 <span data-ttu-id="bcd9a-108">Las aplicaciones afectadas por este cambio pueden encontrar una solución alternativa a este problema de dos formas:</span><span class="sxs-lookup"><span data-stu-id="bcd9a-108">Apps affected by this change can work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="bcd9a-109">Establecer de manera explícita la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> deseada como la primera operación en una tarea asincrónica.</span><span class="sxs-lookup"><span data-stu-id="bcd9a-109">By explicitly setting the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> property as the first operation in an asynchronous task.</span></span>  
  
-   <span data-ttu-id="bcd9a-110">Optar por el comportamiento anterior de que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> no fluyan, mediante la adición del elemento `AppContextSwitchOverrides` siguiente al archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="bcd9a-110">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by adding the following `AppContextSwitchOverrides` element to the application's configuration file:</span></span>  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="bcd9a-111">Optar por el comportamiento anterior de que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> no fluyan, con la configuración mediante programación del siguiente modificador de compatibilidad:</span><span class="sxs-lookup"><span data-stu-id="bcd9a-111">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by setting the following compatibility switch programatically:</span></span>  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bcd9a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcd9a-112">See Also</span></span>  
 [<span data-ttu-id="bcd9a-113">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="bcd9a-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

